---
title: Contribution Guidelines
type: Guidelines & Policies
specs:
  Language: English only
  Verification: Manufacturer spec sheets required
  Format: Markdown with YAML front matter
---
# Contribution Guidelines

Welcome to StageDB! We welcome community contributions to build the most accurate technical audio equipment database. Please follow these guidelines before submitting a pull request.

---

## 1. General Rules

- **English Only**: All documentation, descriptions, specifications, commit messages, and filenames must be written in English.
- **Accurate & Verified Information**: All technical data (frequency ranges, impedances, dimensions, polar patterns, wattage) must come directly from official manufacturer datasheets, manuals, or verified testing. Do not guess or post speculative numbers.
- **No Marketing Fluff**: Keep descriptions objective, technical, and concise. Avoid promotional slogans (e.g., avoid "the best sounding microphone in the world").

---

## 2. Allowed vs. Disallowed Content

### Allowed Content
- Professional audio equipment: Microphones, Mixers, Stageboxes, Power Amplifiers, Speakers, Subwoofers, Line Arrays, and System Processors.
- Discontinued or legacy gear, provided official documentation and specifications exist.
- High-quality, clear product photos with plain backgrounds (saved under `images/<product-slug>/`).

### Disallowed Content
- Consumer non-pro audio gear (e.g. smart speakers, cheap PC gaming headsets, soundbars).
- Subjective reviews, star ratings, or affiliate buying links.
- Copyright-infringing media, watermarked images, or low-resolution screenshots.
- Spam, duplicate articles, or placeholder files without real data.

---

## 3. How to Add or Modify Equipment

### Article Format
Every piece of gear is a Markdown file placed in the appropriate category folder (e.g. `content/02 Microphones/<brand>-<model>.md`).

Each file must start with YAML front matter:

```markdown
---
title: SM7B
brand: Shure
type: Dynamic vocal microphone
image: images/shure-sm7b/sm7b.jpg
alt: Shure SM7B dynamic studio microphone with windscreen
freq_range: [50, 20000]
tags: [dynamic, cardioid, vocal, broadcast, studio]
specs:
  Pattern: Cardioid
  Frequency range: 50–20,000 Hz
  Impedance: 150 Ω
  Sensitivity: -59.0 dB (1.12 mV)
  Connector: 3-pin XLR
---
```

### Body Content
After the front matter, include:
1. A concise overview paragraph explaining what the gear is.
2. `## Key Features`: Bullet points highlighting technical attributes.
3. `## Typical use`: Common real-world professional applications.
4. Wiki links to related gear where applicable using `[[Brand Model]]` syntax.

---

## 4. Mandatory Step: Log in Contributors

Whenever you add or modify any files, you **must** record your contribution in `content/01 Contributors/contributors.md`:

1. Add your name/GitHub handle to the **Contributors** list (if not already listed).
2. Add an entry under **Contribution Log** noting:
   - **Date** (YYYY-MM-DD)
   - **Your Name / GitHub username**
   - **Files modified or added**
   - **Brief description of changes**

### Example:
```markdown
- **2026-10-17** - [@TibbevanZ](https://github.com/TibbevanZ): Added `content/02 Microphones/shure-sm7b.md` and `images/shure-sm7b/sm7b.jpg`.
```

---

## 5. Submission Workflow

1. Fork the repository and create a feature branch (`git checkout -b feature/gear-name`).
2. Add your equipment Markdown file and corresponding images.
3. Update `content/01 Contributors/contributors.md` with your contribution log entry.
4. Verify files follow the naming conventions (lowercase slugs with hyphens for files: e.g. `yamaha-cl5.md`).
5. Commit and open a Pull Request against `main`.
