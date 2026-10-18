# Contributing to StageDB

Thanks for helping out. StageDB is a reference for audio gear, and it is only useful if what it says is **correct**, **written the same way everywhere** and **written by you**. This guide explains how to document an item.

> **Language:** write articles, specs and tags in **English**. That keeps search, sorting and comparing consistent across the whole site. _(Maintainer: change this if you pick another language.)_

## Contents

1. [The five rules](#1-the-five-rules)
2. [How to contribute](#2-how-to-contribute)
3. [Adding a new item](#3-adding-a-new-item)
4. [Names and files](#4-names-and-files)
5. [Specs: standard names and notation](#5-specs-standard-names-and-notation)
6. [Writing style and structure](#6-writing-style-and-structure)
7. [Sources and accuracy](#7-sources-and-accuracy)
8. [Images](#8-images)
9. [Documents, measurements and curves](#9-documents-measurements-and-curves)
10. [Glossary](#10-glossary)
11. [Changing, renaming and removing](#11-changing-renaming-and-removing)
12. [Pull request checklist](#12-pull-request-checklist)
13. [Templates](#13-templates)

---

## 1. The five rules

1. **Every spec has a source.** Never write values from memory. If you are not sure about a value, leave the spec out.
2. **Write in your own words.** Do not copy text from the manufacturer's website or manual, and no marketing phrases.
3. **Only use images you are allowed to use.** Your own photos, or images whose licence permits it. No pictures from web shops or manufacturers without permission.
4. **Use the standard spec names and notation** from [section 5](#5-specs-standard-names-and-notation). That is what makes sorting, comparing and range search work.
5. **Stay neutral.** No "the best", no "amazing". Describe what it is, how it works and what it is used for.

---

## 2. How to contribute

**Small fix** (typo, correcting a spec): open the article on the site and click **Edit on GitHub**. GitHub creates a branch and a pull request for you.

**New item or larger change:**

1. **Fork** the repo (or create a branch if you have write access).
2. Create a branch with a clear name: `add-shure-sm58`, `fix-qsc-k12-2-specs`.
3. Add or change your files (see below).
4. Open a **pull request** and go through the [checklist](#12-pull-request-checklist).
5. A maintainer will review it. Apply their comments in the same branch.

**Commit messages** are short and clear:

```
Add Shure SM58
Fix SM57 impedance
Add cardioid to glossary
```

Prefer **one item** or one logical change per pull request. It is easier to review.

Still working on an article? Start the file name with `_` (`_shure-sm58.md`). The site ignores files like that. Remove the `_` when it is ready.

---

## 3. Adding a new item

1. First check that the item does not exist yet. Search the site for the brand and model.
2. Pick the right folder in `content/` (see [section 4](#4-names-and-files)).
3. Copy the [template](#13-templates) into a new file, for example `content/microphones/shure-sm58.md`.
4. Fill in the front matter. Use the spec names from section 5.
5. Write the text (section 6) and put the sources at the bottom (section 7).
6. Add images in `images/<file-name>/` (section 8).
7. Link to related items with `[[Shure SM57]]`. A link to an item that does not exist yet turns red. That is fine, it shows what is still missing.
8. Open your pull request.

---

## 4. Names and files

### Categories

An item belongs in exactly one folder in `content/`. The folder name becomes the category.

| Folder | What it is for |
| --- | --- |
| `microphones` | Microphones (dynamic, condenser, ribbon, wireless) |
| `speakers` | Loudspeakers, monitors, PA |
| `amplifiers` | Power amplifiers and instrument amplifiers |
| `mixers-interfaces` | Mixing consoles and audio interfaces |
| `headphones-iems` | Headphones and in-ear monitors |

Do not add a **new category** yourself. Discuss it with a maintainer first, for example in an issue.

### File names

- Only **lowercase letters, digits and hyphens**: `brand-model.md`.
- No spaces, no capitals, no accents.
- Brand and model as printed on the device: `shure-sm58.md`, `qsc-k12-2.md`, `behringer-x32.md`.
- Dots in a model name become hyphens: `K12.2` becomes `k12-2`.
- For versions or generations, add them at the end: `focusrite-scarlett-2i2-4th-gen.md`.

The file name decides the page address. **Do not rename files** without a good reason (see [section 11](#11-changing-renaming-and-removing)).

### Title and brand

- `brand`: the manufacturer's official spelling (`Shure`, `Electro-Voice`, `Neumann`).
- `title`: only the model name, as the manufacturer writes it (`SM58`, `U 87 Ai`, `K12.2`). Do **not** put the brand in the title, because the site joins brand and title itself.

---

## 5. Specs: standard names and notation

### Notation of values

| Rule | Good | Bad |
| --- | --- | --- |
| **Number first**, then the unit, with a space between | `300 Ω` | `Ω300`, `300Ω` |
| Comma for thousands, dot for decimals | `1,000 W`, `-54.5 dBV/Pa` | `1.000 W`, `-54,5` |
| Ranges with a hyphen or en dash | `50–15,000 Hz` | `50 to 15000` |
| Conditions in brackets | `55–20,000 Hz (-3 dB)` | `55–20,000 Hz at -3 dB` |
| Standard unit symbols: `Hz`, `kHz`, `Ω`, `dB`, `W`, `V`, `mV/Pa`, `dBV/Pa`, `kg`, `mm` | `127 dB` | `127 decibel` |
| No comments with ` #` in a value | `XLR` | `XLR # balanced` |

For sorting and search the site looks at the **first number** in the value. A value like `300 Ω` is therefore fine. Always use the same unit for the same spec, because the site does not convert anything.

### Standard spec names

Use these names **exactly**, with the same capitals. Leave a spec out if you do not know the value. Only add your own spec if no suitable one exists.

**Microphones**

| Spec | Example |
| --- | --- |
| `Type` | `Dynamic`, `Condenser`, `Ribbon` |
| `Pattern` | `Cardioid`, `Omni, cardioid, figure-8` |
| `Frequency range` | `50–15,000 Hz` |
| `Impedance` | `300 Ω` |
| `Sensitivity` | `-54.5 dBV/Pa` or `28 mV/Pa` |
| `Max SPL` | `117 dB` |
| `Power` | `48 V phantom` |
| `Connector` | `XLR` |

**Speakers**

| Spec | Example |
| --- | --- |
| `Type` | `Powered, 2-way` |
| `Frequency range` | `55–20,000 Hz (-3 dB)` |
| `Max SPL` | `132 dB peak` |
| `Power` | `1,000 W peak` |
| `Woofer` | `12″` |
| `Tweeter` or `Driver` | `1″` |
| `Coverage` | `75° × 75°` |
| `Inputs` | `XLR, TRS` |

**Amplifiers**

| Spec | Example |
| --- | --- |
| `Channels` | `2` |
| `Power at 4 Ω` | `775 W per channel` |
| `Power at 8 Ω` | `475 W per channel` |
| `Class` | `Class D` |
| `Inputs` | `XLR, TRS` |

For instrument amplifiers use `Type` (`Tube combo`), `Power` (`85 W`) and `Speakers` (`2 × 12″`).

**Mixers & interfaces**

| Spec | Example |
| --- | --- |
| `Inputs` | `2` |
| `Outputs` | `2` |
| `Mic preamps` | `32` |
| `Mix buses` | `16` |
| `Resolution` | `24-bit / 192 kHz` |
| `Sample rates` | `44.1 / 48 kHz` |
| `Connection` | `USB-C` |

**Headphones & IEMs**

| Spec | Example |
| --- | --- |
| `Design` | `Open-back`, `Sound-isolating IEM` |
| `Frequency range` | `12–40,500 Hz` |
| `Impedance` | `300 Ω` |
| `Sensitivity` | `105 dB SPL / 1 V` |

**For all categories** you may also use `Weight` (`0.298 kg`) and `Dimensions` (`162 × 51 × 51 mm`).

Missing a spec that comes up often? Propose an addition to this list in an issue, so everyone uses the same name.

### Other fields

- `type`: short description in English, capitalised, no full stop: `Dynamic vocal microphone`.
- `key`: the one spec shown in overview lists, usually the frequency range or the power.
- `tags`: lowercase, singular or the common term, and reuse existing tags. Check `/tags` to see what exists. Examples: `dynamic`, `cardioid`, `vocal`, `studio`, `powered`.
- `freq_range`: `[low, high]` in Hz, the **-3 dB points as stated by the manufacturer**. If they are not stated, leave the field out.

---

## 6. Writing style and structure

- **First sentence:** say what it is. "The SM58 is a dynamic cardioid microphone designed for live vocals."
- **Neutral and factual.** Avoid adjectives like "legendary", "perfect" or "warm sounding" unless you explain them.
- **Short paragraphs.** A few sentences at most.
- **Use the standard headings** where they apply, in this order:

| Heading | Content |
| --- | --- |
| *(introduction, no heading)* | What it is and who it is for. |
| `## Typical use` | What it is used for, as a list. |
| `## Notes` | Particularities: known traits, pitfalls, set-up tips. |
| `## Variants and versions` | Other versions (for example with a switch), generations, regional differences. |
| `## Sources` | Required. See the next section. |

- **Link wisely.** Point to related items with `[[...]]`, especially variants and direct alternatives.
- You do not need to explain **technical terms** that are in the glossary. If a term is missing, add it (section 10).
- No personal opinions, no "I think". If you want to share experience, say clearly what it is about and keep it to what other users can verify.

---

## 7. Sources and accuracy

**Every item has a `## Sources` heading** listing where the specs come from, with links.

```markdown
## Sources
- Shure SM58 product page and specification sheet (retrieved 2026-10-18)
- Shure SM58 user guide, revision 2024
```

For each source, say what it is and, if you know it, the **version or date**. Manufacturers change specs, and an old datasheet can differ.

For the links themselves, preferably also use the `docs:` field in the front matter. They then also appear in the "Documentation" box:

```yaml
docs:
  Datasheet: https://example.com/sm58-datasheet.pdf
```

**How to handle sources:**

- **Preferred:** the manufacturer's official datasheet or manual.
- **Measurements:** independent measurements are fine, as long as you note who measured and under which conditions.
- **Conflicting sources:** state both values and explain the difference in `## Notes`. Do not pick one silently.
- **Not acceptable:** forums, sellers, reviews or "I believe" as a source for a spec.
- **In doubt?** Leave the spec out, or mark it as an estimate: `approx. 120 W`.
- **Units:** do not convert to make it "nicer". Copy the value and unit as the source gives them.
- **Versions:** if you are documenting a newer generation, make a separate item, or mention the difference under `## Variants and versions`.

---

## 8. Images

- **Rights:** only your own photos, or images whose licence allows it (then credit the author and licence in `## Sources`). Without clear permission: do not use it.
- **Location:** `images/<article-file-name>/`, for example `images/shure-sm58/front.jpg`.
- **Names:** descriptive and lowercase: `front.jpg`, `side.jpg`, `back-connectors.jpg`.
- **Format:** `jpg`, `webp` or `png`. Aim for a long side of about 1600 pixels and preferably under 500 kB per file.
- **Shots:** neutral background, good light, the whole device in the picture, and no watermarks or seller logos.
- **Main photo:** `image:` in the front matter. More photos go in `gallery:`.
- **Alt text is required.** Set `alt:` in the front matter and describe what you see: `Shure SM58 with silver grille`. Not "photo 1".
- **SVG:** only for your own diagrams or icons, never a file from the internet.

---

## 9. Documents, measurements and curves

**PDFs:** preferably link to the **manufacturer's official page**. That way it is always the current version and you take no copyright risk. Only put a PDF in the repo yourself (`docs/<file-name>/`) if the licence allows it, and say so in `## Sources`.

**Frequency range (`freq_range`):** the site uses this to draw an *approximate* curve. That is an illustration of the range, not a measurement. Only fill it in if the manufacturer states the range with a tolerance.

**Real measurements (`response`):** supply a CSV with two columns, frequency in Hz and level in dB:

```csv
freq,db
20,-30
100,-6
1000,0
```

Only do this if the measurement is yours or the author gives permission. In the article (under `## Notes` or `## Sources`) describe **who** measured, **with what set-up**, **at what distance/angle** and whether it was **smoothed**. A graph without that information says little.

---

## 10. Glossary

Missing a term that appears in several articles? Create a file in `content/_glossary/`:

```markdown
---
title: Phantom power
aliases: [48V]
---
Direct current sent through a microphone cable to power condenser microphones, usually 48 volts.
```

- The **first sentence** is the short explanation in the tooltip. Make it a clear, stand-alone definition.
- Put common abbreviations and other spellings in `aliases`.
- Keep it short. A term should not have more than a few paragraphs. If you have more to say, make it an article.
- Only the first mention in an article is linked automatically.

---

## 11. Changing, renaming and removing

- **Correcting specs:** change the value and put the new source in `## Sources`. Describe in your pull request what was wrong.
- **Renaming:** the file name decides the address. If you rename a file, the address changes and old links break. First search for `[[links]]` to the item and update them in the same pull request. Only do this with a good reason.
- **Changing category:** move the file to another folder, or set `category:` in the front matter. The address changes here too.
- **Removing:** ask a maintainer first. Merging duplicates is better than deleting them.
- **Discontinued items:** keep an item if a model is no longer sold. Mention it in `## Notes` ("Discontinued in 2023").

---

## 12. Pull request checklist

Copy this into your pull request and tick it off:

```markdown
- [ ] File is in the right folder and named `brand-model.md` (lowercase, hyphens)
- [ ] `title` contains only the model, `brand` is the official spelling
- [ ] `type`, `tags` and `specs` are filled in, using the standard spec names and notation
- [ ] Only specs whose source I know; unknown specs are left out
- [ ] `## Sources` is at the bottom, with links and version or date
- [ ] Text is in my own words, neutral and in English
- [ ] Images are my own or have a permitted licence, and have `alt`
- [ ] No manufacturer PDFs in the repo (link to the official page instead)
- [ ] Links to other items (`[[...]]`) are correct
```

---

## 13. Templates

### General item

```markdown
---
title: Model
brand: Brand
type: Short description of the product
image: images/brand-model/front.jpg
gallery: [images/brand-model/side.jpg]
alt: Describe what the photo shows
freq_range: [20, 20000]
tags: [tag-one, tag-two]
key: 20–20,000 Hz
specs:
  Type: Dynamic
  Frequency range: 20–20,000 Hz
  Impedance: 200 Ω
  Connector: XLR
docs:
  Datasheet: https://example.com/official-datasheet.pdf
---
The Model is a [type] from Brand, designed for [purpose]. One or two sentences on what makes it distinct, without marketing words.

## Typical use
- First use
- Second use

## Notes
Facts that help someone choosing or setting it up.

## Variants and versions
Other versions and what changed. Link related items with [[Brand Other Model]].

## Sources
- Brand Model specification sheet (retrieved YYYY-MM-DD)
- Brand Model user guide, revision YYYY
```

### Microphone, filled-in example

```markdown
---
title: SM57
brand: Shure
type: Dynamic instrument microphone
image: images/shure-sm57/front.jpg
alt: Shure SM57 with silver grille
freq_range: [40, 15000]
tags: [dynamic, cardioid, instrument]
specs:
  Type: Dynamic
  Pattern: Cardioid
  Frequency range: 40–15,000 Hz
  Impedance: 150 Ω
  Sensitivity: -56 dBV/Pa
  Connector: XLR
docs:
  Datasheet: https://example.com/sm57-datasheet.pdf
---
The SM57 is a dynamic cardioid microphone used mostly to close-mic instruments and amplifiers. See also the [[Shure SM58]], which is built for vocals.

## Typical use
- Snare drum
- Guitar cabinets
- Brass

## Sources
- Shure SM57 specification sheet (retrieved 2026-10-18)
```

> The values in this example are only there to show the layout. Always check them against the manufacturer's datasheet.

---

## Questions

Unsure about something in this guide, or missing a category or spec? Open an **issue** in the repo. You can also just start with a draft pull request, and the maintainers will think along.

**Content licence:** _(maintainer: fill in the licence here, and add that contributors confirm they have the rights to what they submit.)_
