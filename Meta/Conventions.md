---
type: meta
tags: [meta]
---

# Conventions

## Folders
| Folder | Contents |
|--------|----------|
| `Books/` | One note per book. Source of truth for status and tier |
| `Reviews/` | In-depth reviews: `<Title> - Review` |
| `Reading Notes/` | Chapter summaries and quotes: `<Title> - Notes` |
| `Templates/` | Note templates (core Templates plugin) |
| `Meta/` | Tier system, conventions |
| `Attachments/` | Covers and images |

## Status values (`status:`)
- `read` · `reading` · `want-to-read` · `dropped`

## Tags
- `#book` · `#review` · `#reading-note` · `#dashboard` · `#meta`
- Genres: `genre: [nonfiction, productivity]` in frontmatter (no `#` needed)

## Links
- Book ↔ review ↔ notes link via `book: "[[Title]]"` in frontmatter.

## Required plugins
- Core: Templates
- Community: Dataview (for the dashboard)
