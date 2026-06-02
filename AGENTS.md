# Beauty knowledge base — agent instructions

This repo is Isabel's personal beauty second brain: face blueprint, products, routines, skin health, hair, and session learnings. Notes are plain Markdown with YAML frontmatter so humans and agents can read, link, and update them consistently.

## Goals

1. **Grow knowledge** — capture research, video takeaways, and GP/derm outcomes without losing context.
2. **Refine routines** — step-by-step routines with products, timing, placement, and technique; flag conflicts (e.g. water- vs silicone-based layers).
3. **Process new information** — everything new lands in `inbox/` first, then is split into the right note(s) with backlinks.
4. **Support critique** — enough detail on each application step that an agent can review technique, placement, and product fit against `wiki/me/face-blueprint.md`.

## Vault layout (PARA + wiki)

| Path | Purpose |
|------|---------|
| `inbox/` | Unprocessed captures: doc dumps, quick notes, paste-from-phone |
| `projects/` | Time-bound goals (GP visit, product shade hunt, Accutane phase) |
| `areas/` | Ongoing standards: daily makeup, skincare, hair, style, lifestyle-for-skin |
| `resources/` | Stable reference: retailers, ingredient lookups, shopping lists |
| `wiki/` | Evergreen, linked knowledge: you, techniques, atomic learnings |
| `journal/` | Dated sessions: what you did, what happened, what to change |
| `archive/` | Completed projects and superseded notes |
| `templates/` | Copy when creating new notes |

**Map of existing root files** (migrate when convenient):

- `understanding-my-features-notes.md` → canonical home: `wiki/me/face-blueprint.md`
- `owned-products-my-makeup-collection.md` → `resources/products/owned-collection.md`
- `TO DO.md` → tasks live in `projects/` or project note checklists; keep a single `projects/_index.md` for overview
- `Things to improve.md` → fold items into `wiki/learnings/` or relevant `areas/` note
- `google-docs-dump-to-process.md` → `inbox/`; process then archive or delete sections

## Note types and frontmatter

Every new note should start from a template in `templates/`. Required frontmatter fields by type:

- **All notes:** `type`, `status` (`draft` \| `active` \| `archived`), `updated` (YYYY-MM-DD)
- **Routine** (`type: routine`): `area` (makeup \| skincare \| hair), `time_of_day` if relevant
- **Product** (`type: product`): `brand`, `name`, `shade`, `owned` (true/false), `incidecoder_url` if known
- **Learning** (`type: learning`): `topic`, `confidence` (hypothesis \| tested \| confirmed)
- **Journal** (`type: journal`): `date`, `context` (work \| event \| practice)
- **Project** (`type: project`): `due`, `done` (false until archived)

Use wikilinks for relationships: `[[face-blueprint]]`, `[[routine-makeup-daily]]`, `[[product-nars-oslo]]`.

## Processing inbox (CODE)

When the user adds a dump or asks to process `inbox/`:

1. **Capture** — leave raw input in `inbox/` until processed (do not delete without confirmation).
2. **Organize** — extract bullets into the smallest useful notes; prefer updating an existing note over creating duplicates.
3. **Distill** — one atomic learning per insight in `wiki/learnings/`; link to face blueprint or routine.
4. **Express** — update routines, product notes, or `projects/` checklists; add open questions to `wiki/questions.md`.

**Conflict rule:** If new text contradicts an active routine (e.g. different foundation product), update the routine note and add a short `## Changelog` entry with date — do not silently overwrite without mentioning it to the user.

**Duplicate rule:** Same fact in multiple places → one canonical note, others link to it.

## Domain conventions

- **Placement** must reference `wiki/me/face-blueprint.md` (inverted triangle, deep set eyes, deep winter, etc.).
- **Products** — check compatibility (water/silicone/oil); link INCIDecoder when verifying ingredients: https://incidecoder.com/
- **Skin health** — separate `areas/skincare/` from makeup; hormonal/acne context stays in area + GP project notes.
- **Journal** — after full-face or significant practice, encourage a short `journal/YYYY-MM-DD-*.md` entry.

## What not to do

- Do not invent product shades, medical advice, or diagnoses.
- Do not commit secrets or API keys.
- Do not create huge monolithic docs; split by note type.
- Do not remove the user's voice from learnings; quote their wording when it matters ("bright lip takes focus from eyes").

## Helpful commands for the user

- "Process my inbox" — run CODE on `inbox/`
- "Critique today's makeup routine" — read active routine + face blueprint + latest journal
- "Add learning: …" — append to `wiki/learnings/` or create from template
- "What's outdated?" — compare `inbox/`, product notes, and routines for conflicts
