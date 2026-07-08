# health-and-beauty

Personal health & beauty second brain: face blueprint, products, routines, skin health, hair, and session journals — in Markdown for you and for agents.

## Start here

- **[Knowledge base setup](docs/knowledge-base-setup.md)** — folder layout, workflows, migration from Google Docs
- **[AGENTS.md](AGENTS.md)** — how Cursor (and other agents) should read, write, and process notes
- **`inbox/`** — paste new dumps; then ask: *"Process my inbox"*

## Structure (short)

| Folder | Contents |
|--------|----------|
| `wiki/me/` | Face blueprint, feature priority |
| `areas/` | Ongoing routines (makeup, skincare, **hair**, style) |
| `areas/hair/` | Hub, wash/between-wash routines, experiment tracker — start at `areas/hair/_index.md` |
| `wiki/hair/` | Hair reference (e.g. Abbey Yung method, product matching) |
| `resources/` | Products, shops (migrate collection here) |
| `projects/` | GP visit, shade hunts, etc. |
| `journal/` | Dated application logs |
| `templates/` | New note starters |

We keep a journal after significant makeup sessions. Unanswered questions live in `wiki/questions.md`.

## Research resources

### [INCIDecoder](https://incidecoder.com/)

Use this site to look up products and decode their INCI ingredient lists.

- Search by **product name** or browse **ingredients** individually.
- Each ingredient page explains what it does (e.g. soothing, antioxidant), irritancy, and links to sources.
- Useful when you have a label or full INCI list and want plain-language context before comparing or logging products here.

Complements programmatic lookups via `openbeautyfacts.py` (Open Beauty Facts API); INCIDecoder is better for human-readable ingredient breakdowns on specific retail products.