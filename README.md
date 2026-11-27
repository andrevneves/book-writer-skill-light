<div align="center">

# ✦ book-writer-light ✦

### *A context-light fork of Book Writer*

*Master-class fiction · Automated story memory · Book-level pacing · Lean context loading*

[![Version](https://img.shields.io/badge/version-0.4.0-8957e5?style=flat-square)](./CHANGELOG.md)
[![License](https://img.shields.io/badge/license-MIT-2ea043?style=flat-square)](./LICENSE)
[![Docs](https://img.shields.io/badge/docs-usage_guide-f78166?style=flat-square)](./docs/USAGE.md)

</div>

---

## Fork Notice

Book Writer Light is a fork of [kshanxs/book-writer-skill](https://github.com/kshanxs/book-writer-skill/).

This fork keeps the original book-writing and memory-bank workflow, but renames the Codex skill to `book-writer-light` and prioritizes smaller, task-specific context loading. The fork is necessary for projects where the full Book Writer workflow is useful, but bulk-loading memory-bank and reference material makes ordinary writing turns slower, noisier, or more expensive than needed.

## 🚀 Installation

```bash
npx skills add https://github.com/flaviobeck/book-writer-skill-light --skill plugins/book-writer-light/skills/book-writer-light
```

To update later:

```bash
npx skills update book-writer-light
```

### Other agents

Other agents do not necessarily consume Codex plugins directly. This repository includes bridge instruction files for common agent conventions:

- `AGENTS.md`
- `CLAUDE.md`
- `.github/copilot-instructions.md`

For agents such as Claude, Devin, opencode, Copilot, or similar tools, point the agent at `plugins/book-writer-light/skills/book-writer-light/SKILL.md` and ask it to follow that file for book-writing tasks.

---

## 🧪 Testing

Validate the skill and plugin from the repository root:

```bash
ruby -e 'require "yaml"; YAML.load_file("plugins/book-writer-light/skills/book-writer-light/assets/book-memory-bank/Core/context_index.yml"); puts "context_index yaml ok"'
python3 <skill-creator>/scripts/quick_validate.py plugins/book-writer-light/skills/book-writer-light
python3 -B plugins/book-writer-light/skills/book-writer-light/scripts/build_context_pack.py plugins/book-writer-light/skills/book-writer-light/assets --task draft --target book-memory-bank/Core/Templates/scene_card_template.md --max-file-chars 2200
python3 <plugin-creator>/scripts/validate_plugin.py plugins/book-writer-light
git diff --check
```

Then run a live smoke test in a fresh project:

```text
Use $book-writer-light to start a new book project.
```

## 💬 Start writing

Just tell your AI assistant what you want:

```text
Let's start building a new book
Write a rhyming picture book about a shy dragon for ages 4-6
I have some notes already. Here's my outline: ./outline.md
```

It asks one question at a time, and you can skip any of them.

## ✨ What you get

- 🧠 **Lasting memory:** characters, plot, world, and progress carry across sessions.
- ✍️ **Craft for your genre:** fiction, non-fiction, history, popular science, and children's books.
- 🗺️ **Story planning:** outlines, pacing blueprints, scene cards, and character arcs.
- 🔍 **Careful revision:** continuity checks and focused passes, with a backup before every edit.
- 📦 **Ready to publish:** Word export, blurbs, synopses, query letters, and cover prompts.

## 🗣️ Things you can say

| Say this | What happens |
|---|---|
| `Write chapter 3` | Drafts the chapter from your book's memory |
| `Do a Dialogue Pass on chapter 2` | Sharpens subtext and character voices |
| `Outline all chapters in parallel` | Launches background agents for chapter outlines |
| `Review all chapters in parallel` | Launches background agents to edit and review drafted chapters |
| `Check continuity` | Flags contradictions across chapters |
| `Update memory bank` | Brings the book's memory up to date |
| `Write a query letter` | Builds a pitch from your story |
| `Write a back-cover blurb` | Generates a blurb from your memory bank |
| `Compile the book` | Combines your chapters into one manuscript |

**→ [Full command reference](./docs/FEATURES.md#-command-reference)**

---

## 📁 Your project

```text
YourBook/
├── Chapters/          Your book
├── Outlines/          Story and chapter plans
├── Research/          Facts and continuity reports
├── Revisions/         Automatic backups
├── Manuscript/        Compiled book
└── book-memory-bank/  What the AI remembers
```

---

## 🤝 Companion skills

- 🔬 **[Research Dojo](https://github.com/kshanxs/skill-dojo/tree/main/skills/research-dojo)** checks facts, dates, and sources for non-fiction.
- 🖋️ **[Calligraph Sensei](https://github.com/kshanxs/skill-dojo/tree/main/skills/calligraph-sensei)** polishes and proofreads prose while keeping your voice.

## 📝 Changelog

See [CHANGELOG.md](./CHANGELOG.md) for details on all versions and releases.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

Copyright © 2026 [Shubhanshu Shukla](https://github.com/kshanxs). All rights reserved.

---

<div align="center">
<sub>MIT License · Made by <a href="https://github.com/kshanxs">Shubhanshu Shukla</a> for authors who care about their craft.</sub>
</div>
