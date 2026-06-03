# Setting up your beauty second brain

This repo is already the right foundation: **local Markdown in git**, editable in Cursor, and optional **Obsidian** pointed at the same folder if you want a graph view. You do not need a separate app to start.

## Why this shape

Your Google Docs dump mixes six kinds of information that fight each other in one file:

| Kind | Examples from your dump | Where it lives |
|------|-------------------------|----------------|
| **Who you are (structure)** | Eye shape, deep winter, inverted triangle | `wiki/me/face-blueprint.md` |
| **What you do (procedure)** | 10-step makeup order, under-eye technique | `areas/makeup/routine-*.md` |
| **What you own** | Rare Beauty blush, Nars Oslo | `resources/products/*.md` |
| **What you learned** | "Bright lip steals focus from eyes" | `wiki/learnings/*.md` |
| **What you're fixing** | Orange blush, oily forehead at 1pm | `journal/` + `Things to improve` |
| **What you're pursuing** | GP spironolactone, shade testing Saturday | `projects/*.md` |

Separating these lets you **add new facts without rewriting whole docs**, and lets an agent **critique a routine** without rereading 500 lines of acne diet notes.

## Recommended stack

| Layer | Tool | Role |
|-------|------|------|
| Storage | This git repo | Own your data; version history |
| Editing | Cursor | Agents read `AGENTS.md` + notes |
| Optional UI | [Obsidian](https://obsidian.md) | Graph, daily note, mobile (same folder) |
| Ingredients | [INCIDecoder](https://incidecoder.com/) | Per-product breakdown (linked from product notes) |
| Optional API | `openfoodfacts` (see `requirements.txt`) | Bulk/barcode lookup when you add scripts |
| Capture | `inbox/` | Paste dumps, voice-to-text, future Google export |

You already listed Google Docs MCP in `TO DO.md` — until then, **export or paste into `inbox/`** and ask Cursor to "process inbox."

## Folder map (PARA + wiki)

```
beauty/
├── AGENTS.md              # how agents should read/write
├── inbox/                 # raw, unprocessed
├── projects/              # finishable (GP visit, shade hunt)
├── areas/                 # ongoing routines & standards
│   ├── makeup/
│   ├── skincare/
│   └── hair/              # _index, routines, experiments.md
├── resources/             # products, shops, references
├── wiki/
│   ├── me/                # face blueprint (canonical you)
│   ├── hair/              # evergreen hair methods & matching rules
│   ├── learnings/         # one insight per file when possible
│   └── questions.md       # open research queue
├── journal/               # dated sessions
├── archive/
└── templates/
```

## Workflows

### 1. New information arrives

1. Drop it in `inbox/` (full dump, one bullet, link from a video).
2. Say: **"Process inbox"** (in Cursor).
3. Agent splits content into notes, links `[[face-blueprint]]`, flags conflicts.
4. You skim changes; raw dump moves to `archive/inbox/` or stays with a "processed" date in frontmatter.

### 2. Refine a routine

1. Open `areas/makeup/routine-daily.md` (create from template).
2. One section per step: product links, wait times, placement, brush.
3. After a real application → `journal/YYYY-MM-DD-work.md`.
4. Move "too orange blush" style notes into learnings + tweak routine.

### 3. Grow reference knowledge

- **Atomic learnings** beat long lists (easier to link and search).
- **Questions** go to `wiki/questions.md` until answered; then answer becomes a learning + routine update.

### 4. Monthly review (5 minutes)

- Archive done `projects/`
- Scan `wiki/questions.md`
- Merge duplicate product mentions
- Check routines still match what you actually use (your dump still mentions BareMinerals while collection notes mention Nars — pick canonical in product notes)

## Migrating what you already have

Do this gradually; no big-bang required.

1. **Face blueprint** — copy `understanding-my-features-notes.md` → `wiki/me/face-blueprint.md`, add frontmatter, keep old file as redirect or delete when happy.
2. **Products** — split `owned-products-my-makeup-collection.md` into one note per product (or a table in `owned-collection.md` plus links).
3. **Dump** — process `inbox/google-docs-dump-to-process.md` section by section (makeup steps → routine; acne list → `areas/skincare/`; journal bit → `journal/2025-05-26-work.md`).
4. **TO DO** — each bullet becomes a `projects/` note or checklist item with links.

## Extensibility later

- **Obsidian plugins:** Templates, daily notes, Dataview (queries on frontmatter).
- **Scripts:** Python + Open Beauty Facts for barcode/INCI batch import into `resources/products/`.
- **MCP:** Google Docs → `inbox/` automation (your existing idea).
- **Critique loop:** Journal entry + routine + blueprint → agent suggests one change per session.

## First session checklist

- [ ] Read `AGENTS.md`
- [ ] Process first inbox file (the Google dump)
- [ ] Create `wiki/me/face-blueprint.md` from existing features doc
- [ ] Create one active makeup routine from dump steps 387–429
- [ ] Log today's journal entry under `journal/`
- [ ] Add open questions from dump to `wiki/questions.md`
