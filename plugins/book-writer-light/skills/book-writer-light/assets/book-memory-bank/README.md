# Book Memory Bank

This folder holds what your AI assistant needs to remember about your book between sessions. Your assistant reads and updates these files for you, so you do not need to manage them by hand.

## What's Inside

```text
book-memory-bank/
├── Core/
│   ├── context_index.yml       Compact routing index, read first
│   ├── projectbrief.md          Concept, scope, and goals
│   ├── story_structure.md       Themes, structure, and narrative patterns
│   ├── world_and_characters.md  World rules and character profiles
│   ├── activeContext.md         Current focus and memory file index
│   ├── progress.md              Completion tracking
│   └── Templates/               Starting points for optional documents
├── Style/
│   └── style_guide.md           Voice, tone, and formatting rules
└── Production/
    ├── AI_Generation/           Cover prompt templates
    └── Scripts/                 Manuscript and Word export tools
```

The assistant starts with `Core/context_index.yml`, which lists what each file holds, so it only loads the files a task needs. It keeps that index up to date as the memory changes.

Your actual book lives outside this folder:

```text
YourBook/
├── Chapters/    Prologue.md, Chapter01.md, Interlude01.md, Epilogue.md
├── Outlines/    Master_Outline.md and Chapter_Outlines/
├── Research/    Research tracker and continuity reports
├── Revisions/   Snapshots made before chapters are revised
└── Manuscript/  Compiled book files
```

## How to Use It

Talk to your assistant naturally:

```text
Write the outline for Chapter 1
Write Chapter 1
Update memory bank
Check continuity
Compile the book
```

A good rhythm is outline, review, draft, review, then update memory. Read each chapter as it is written, because early corrections are much easier than late ones.

## Exporting Your Book

See [Production/README.md](Production/README.md) for the manuscript and Word export commands.
