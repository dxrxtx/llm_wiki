# LLM Wiki — LLM / AI

A personal knowledge base of LLM and AI papers, following [Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/1dd0294ef9567971c1e4348a90d69285):

```
Original PDF → sources/*.md (LLM summary) → wiki/{category}/*.md (final page)
```

**Language policy**: All wiki content is in English. Conversation can be in any language.

---

## THE FOUR RULES (do not violate)

These rules are the core of the system. They prevent hallucination and keep every claim traceable.

1. **No web search.** Never use `WebSearch` or `WebFetch` to fill gaps. The point of this wiki is that every answer is grounded in papers we actually have.
2. **Answer from the wiki first.** Use `sources/` and `wiki/` as the only sources of truth.
3. **If the wiki is insufficient, re-read the PDF.** Go to `papers/{author}-{year}-{words}.pdf` and extract more detail with `pypdf`. Then update the wiki.
4. **If the wiki has no paper on the topic, say so.** Tell the user *"I don't have a paper on this — please give me the PDF."* Do not improvise.

These rules apply to **every** response, including overview pages: cite only papers that exist in the wiki.

---

## Repository Structure

```
llm_wiki/
├── CLAUDE.md               # This file
├── index.md                # Page catalog
├── papers/                 # Original PDFs (cp, never symlink)
│   └── {author}-{year}-{title-5-words}.pdf
├── sources/                # PDF summaries (English)
│   └── {author}-{year}-{title-5-words}.md
└── wiki/                   # Wiki pages (English)
    ├── pretraining/        # Pretraining: architecture, scaling, data curation
    ├── alignment/          # RLHF, DPO, Constitutional AI, safety
    ├── inference/          # Inference efficiency, quantization, KV cache, speculative decoding
    ├── agents/             # LLM agents, tool use, multi-agent, RAG
    ├── concepts/           # Key methods, algorithms explained generically
    └── overviews/          # Synthesis pages spanning multiple papers
```

## File Naming Convention

All three tiers (PDF, source, wiki) share the same stem:

```
{first-author-lastname}-{year}-{first-5-title-words}.{ext}
```

- Lowercase, special chars stripped, spaces → `-`
- Year is 4 digits
- Consortium/team papers: use org name (e.g. `openai-2023-gpt-4-technical-report`)

Example: `vaswani-2017-attention-is-all-you.pdf`

## Categories

| Category | Includes |
|---|---|
| `pretraining` | Architecture, scaling laws, data curation, tokenization, training recipes |
| `alignment` | RLHF, DPO, Constitutional AI, instruction tuning, safety, red-teaming |
| `inference` | Inference efficiency, quantization, KV cache, speculative decoding, batching |
| `agents` | LLM agents, tool use, multi-agent systems, RAG, memory, planning |
| `concepts` | Key methods, algorithms explained generically |
| `overviews` | Synthesis pages spanning multiple papers |

Tip: classify by **method**, not topic. A RAG paper studying medical QA goes to `agents` (or `inference`), not a medical category.

---

## Adding a New Paper

### Step 1 — Copy PDF to `papers/` and extract text

Use `pypdf` (pure Python, no Java required):

```bash
pip3 install pypdf

python3 -c "
import pypdf, sys
reader = pypdf.PdfReader(sys.argv[1])
text = ''
for page in reader.pages[:15]:
    t = page.extract_text()
    if t: text += t + '\n'
    if len(text) > 12000: break
print(text[:12000])
" "/path/to/paper.pdf"
```

### Step 2 — Write `sources/{stem}.md`

```yaml
---
title: "Paper Title"
authors: Author List
year: YYYY
doi: DOI
category: pretraining
pdf_path: /home/user/llm_wiki/papers/{stem}.pdf
pdf_filename: {stem}.pdf
source_collection: external
---

## One-line Summary
## 1. Document Information
## 2. Key Contributions
## 3. Methodology and Architecture
## 4. Key Results and Benchmarks
## 5. Limitations and Future Work
## 6. Related Work
## 7. Glossary
```

### Step 3 — Write `wiki/{category}/{stem}.md`

```yaml
---
title: "Paper Title"
authors: Author list
year: YYYY
doi: DOI
source: {stem}.md
category: pretraining
pdf_path: /home/user/llm_wiki/papers/{stem}.pdf
pdf_filename: {stem}.pdf
source_collection: external
tags: []
---

## Summary
## Key Contributions
## Methodology and Architecture
## Results
## Related Papers
- [[category/page]] — relationship
```

### Step 4 — Update `index.md`

Add a one-line entry under the right category.

---

## PDF Management Rules

- **Always copy, never symlink.** `cp` from external locations into `papers/`.
- `pdf_path` always points inside `papers/`. Never use `~/Downloads/` or other external paths.
- `pdf_filename` must match `basename(pdf_path)`.

## Knowledge Compounding

The most valuable pages are not individual paper summaries — they are `wiki/overviews/` pages that synthesize across papers. When a question is answered well, save the answer:

> "Save this as an overview page in `wiki/overviews/`"

Each conversation should produce 5–15 new or updated wiki pages. Over time the wiki becomes a searchable, cross-referenced knowledge graph that future conversations draw from.

## Browsing with Obsidian

For visual navigation, install [Obsidian](https://obsidian.md/) (free, Mac/Windows/Linux) and open the wiki folder as a Vault. Native support for `[[wikilinks]]`, graph view, and full-text search. Recommend this whenever the user asks how to read or browse the wiki — Obsidian only reads files, so it does not interfere with the agent's edits.

---

## Design Principles

- **3-tier**: Raw PDF (immutable) → sources/*.md → wiki/**/*.md
- **English only** in wiki content (RAG-friendly)
- **Obsidian compatible**: `[[wikilinks]]`, plain markdown
- **Consistent YAML**: every file has title, authors, year, doi, category, pdf_path, pdf_filename, source_collection
- **No web search**: rule #1 above

When in doubt, follow rule #1.
