# Design Leadership Wiki

A second brain and learning toolkit for design leadership, built by [Rasagy Sharma](https://rasagy.in). This repo collects structured notes from books, atomic ideas extracted from those notes, and answers to design leadership questions — all connected as a personal knowledge base and explored with Claude AI skills.

---

## Folders

| Folder | Purpose |
|---|---|
| [ref/](ref/) | Source books in EPUB/MOBI format — the raw material everything else is derived from |
| [notes/](notes/) | Structured chapter-by-chapter summaries of each book, with key ideas, quotes, and cross-cutting themes |
| [ideas/](ideas/) | Atomic, Zettelkasten-style notes — single self-contained concepts extracted from book summaries |
| [q&a/](q&a/) | Research-backed answers to design leadership questions, with references to relevant ideas and further reading |

---

## Claude Skills & Commands

These are AI-assisted workflows available in this project via Claude Code.

### `/summarize` — Summarize a book
Takes an EPUB, MOBI, PDF, or Markdown file from `ref/` and produces a structured chapter-by-chapter summary in `notes/`. Each summary includes a two-sentence book thesis, key ideas per chapter, notable quotes, and a cross-cutting themes table.

### `/atomize` — Atomize notes into ideas
Reads a file from `notes/` and extracts every self-contained concept into individual atomic idea files in `ideas/`. Each idea file is standalone, titled as a succinct phrase, and linked back to its source chapter.

### `/ask` — Ask a design leadership question
Researches an answer to any design leadership question by searching existing `ideas/` and `notes/`, supplementing with web research, and saving a structured response to `q&a/`. Also generates three Socratic follow-up questions and five curated resources.