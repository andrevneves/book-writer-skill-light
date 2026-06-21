# Changelog

All notable changes to the `book-writer` skill will be documented in this file.

## v2.2.0 — 2026-06-21
- **Sequential Prose Drafting Enforced:** Prohibited parallel prose drafting to resolve the narrative dependency paradox. Sequential drafting is now the default, restricting concurrent agents strictly to outlining, scene cards, and reviews.
- **Smart-Reading Protocol:** Transitioned core workflow from bulk-loading all memory bank files to an on-demand protocol indexed via `activeContext.md` to prevent latency and prompt bloat.
- **Reference-Based Spinoff Model:** Replaced copy-paste character inheritance in spinoffs with relative markdown link referencing, solving the "split-brain" data synchronization issue.

## v2.1.1 — 2026-06-18
- **Popular Science & Tech History Support:** Added a new `popscience_history_rules.md` reference file to support popular science, technology history, and narrative non-fiction books.
- **Checklist Quality Gates:** Integrated new checkpoints into `revision_checklist.md` to verify tense split, visual analogies, chronological tech accuracy, and paper quote formatting.

## v2.1.0 — 2026-06-18
- **World & Tech Gita (Story Gitas) Template:** Added the new `world_gita_template.md` template file to support deep technology, magic systems, and lore documentation.
- **Advanced Prose Style Guidelines:** Codified guidelines for Readability First (High Readability Standard), Narrator Warmth, Tech/Magic Introduction Rule (One-Sentence Context Rule), and Character Name/Number conventions in `author_rules.md`.
- **Integrated Quality Gates:** Updated `revision_checklist.md` with checkpoints to verify readability, warmth, name usage, and tech/magic introductions during chapter reviews.
- **Protocol & Workflow Updates:** Integrated World Gita files (`world_gita.md`) into the core memory bank flowcharts, update protocols, and review checklists.

## v2.0.1 — 2026-03-19
- **Memory Bank File Management:** Added guidance on when to split `world_and_characters.md`. Growing is expected — only split at ~200–300KB, and split by concern (characters vs. deep lore), never by character.

## v2.0
- Initial public release with full memory bank system, parallel drafting, spinoff support, and publishing toolkit.
