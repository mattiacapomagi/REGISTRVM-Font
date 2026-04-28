# Contributing to REGISTRVM

Thank you for your interest in contributing to REGISTRVM. This is an open-source typographic revival project born at RUFA – Rome University of Fine Arts, and we welcome contributions from type designers, typographers, developers, and anyone passionate about historical letterforms.

Before contributing, please read this document carefully. It defines how to work with the source, what kinds of contributions are welcome, and the standards we expect.

---

## Table of Contents

- [Project Philosophy](#project-philosophy)
- [What We Need](#what-we-need)
- [Before You Start](#before-you-start)
- [Setting Up Your Environment](#setting-up-your-environment)
- [Contribution Workflow](#contribution-workflow)
- [Working with the Source File](#working-with-the-source-file)
- [Design Standards](#design-standards)
- [Naming Conventions](#naming-conventions)
- [Exporting the Font](#exporting-the-font)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Reporting Issues](#reporting-issues)
- [Code of Conduct](#code-of-conduct)

---

## Project Philosophy

REGISTRVM is not a generic Garamond revival. It is a typographic revival grounded in a specific historical specimen from the Vatican Archives, reinterpreted with careful attention to its original personality: compressed proportions, sharp serifs, high contrast, and a monumental quality suitable for display use.

Every contribution must respect this direction. The goal is to **extend and refine** the typeface while preserving the historical character of the source material. If you are unsure whether a proposed change aligns with the project's vision, open a Discussion or an Issue before investing time in drawing.

---

## What We Need

Contributions are welcome in the following areas, roughly in order of priority:

### High Priority
- **True lowercase set** — The most significant missing piece. The current font maps lowercase Unicode to uppercase forms, which is a known limitation. A historically informed lowercase design based on Garamond-style old-style roman forms is the most impactful contribution possible.
- **Numerals (0–9)** — Oldstyle figures preferred, consistent with the overall design language.
- **Spacing and kerning improvements** — The current spacing is functional but not refined. Systematic optical spacing corrections are welcome.

### Medium Priority
- **Expanded accented Latin coverage** — Extend coverage beyond the current A, E, I, O, U variants to support more European languages.
- **Additional punctuation and symbols** — Fill in gaps in the current symbol set.
- **Additional stylistic alternates** — Alternate forms for specific letters, especially those with historical variants in the source specimen.

### Lower Priority / Exploratory
- **New weights** — A bold or light variant. Any new weight must be optically corrected, not mechanically interpolated.
- **New styles** — Italic or small caps. These are significant undertakings and should be discussed before starting.

### Non-Drawing Contributions
- **Bug reports** — Spacing errors, glyph rendering issues, missing Unicode mappings, incorrect metrics.
- **Testing** — Real-world layout testing and specimens help identify issues.
- **Documentation** — Improvements to the README (including the Character Set table), specimen images, or usage examples.

---

## Before You Start

1. **Open an Issue or Discussion first** for any significant change (new glyph category, structural changes, new weights). This prevents duplicated effort and ensures alignment with the project direction before drawing begins.
2. **Check open Issues and Pull Requests** to avoid duplicating work already in progress.
3. **Read the Design Standards section** below before touching any glyph.

---

## Setting Up Your Environment

### Required Software

| Tool | Purpose |
|---|---|
| [Glyphs 3](https://glyphsapp.com/) | Primary source file editor (`.glyphs` format) |
| macOS | Recommended OS for Glyphs and font QA |

> **Note:** Glyphs 2 may be partially compatible, but Glyphs 3 is the reference editor for this project. Fontforge or other editors are not officially supported — if you use them, ensure the exported `.otf` is verified against the design before submitting.

### Setup Steps

1. **Fork** the repository on GitHub.
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/<your-username>/REGISTRVM-Font.git
   cd REGISTRVM-Font
   ```
3. Open `REGISTRVM.glyphs` in Glyphs 3.
4. Review the existing masters, components, and anchor structure before making changes.

---

## Contribution Workflow

```
Fork → Branch → Edit Source → Export OTF → Test → Pull Request
```

### Step-by-step

1. **Create a branch** from `main` with a descriptive name:
   ```bash
   git checkout -b feature/lowercase-set
   git checkout -b fix/kerning-av-pair
   git checkout -b feat/numerals
   ```

2. **Make your changes** in `REGISTRVM.glyphs` only. Do not edit the compiled `.otf` file manually — it is always a build artifact.

3. **Export a new `.otf`** from Glyphs (see [Exporting the Font](#exporting-the-font)).

4. **Test the font** in a real layout environment (see testing checklist below).

5. **Update `README.md`** if your contribution adds or removes glyphs. The **Character Set** table in the README must stay in sync with the actual font coverage. If you added a new glyph category (e.g., numerals, lowercase), add a corresponding row to the table. If you expanded an existing category, update the detail column accordingly.

6. **Commit** your changes with a clear, descriptive message:
   ```bash
   git add REGISTRVM.glyphs REGISTRVM.otf README.md
   git commit -m "feat: add numerals 0-9, oldstyle figure style"
   ```

6. **Push** to your fork and **open a Pull Request** against `main`.

### Commit Message Format

Use the following prefixes for consistency:

| Prefix | Use Case |
|---|---|
| `feat:` | New glyphs, new features |
| `fix:` | Bug fixes, spacing/kerning corrections |
| `refine:` | Visual refinements to existing glyphs |
| `docs:` | Documentation changes only |
| `chore:` | Non-drawing changes (metadata, export settings) |

Example:
```
feat: add lowercase a–z based on Garamond old-style forms
fix: correct sidebearing on glyph V causing tight pair in AV
refine: adjust contrast on uppercase Q tail
```

---

## Working with the Source File

The canonical source is `REGISTRVM.glyphs`. All design work must happen here.

### Important Rules

- **Do not rename existing glyphs** without documenting the reason. Glyph names affect Unicode mapping and feature code.
- **Do not delete existing glyphs**, even if you intend to redraw them. Replace the content, not the glyph slot.
- **Do not change font metrics** (UPM, ascender, descender, cap height, x-height) without explicit discussion in an Issue first. Metric changes can break existing documents using the font.
- **Maintain existing components** where possible. If a glyph uses a component (e.g., a diacritic built from a base letter + anchor), preserve the component structure rather than flattening it.
- **Anchors** on base glyphs and marks must be preserved and correctly positioned if you modify the affected glyphs.

### OpenType Features

If your contribution requires new OpenType features (e.g., `ss01` for a stylistic alternate, `onum` for oldstyle figures), add them in the appropriate feature code block inside Glyphs. Document the feature and its intent in the Pull Request description.

---

## Design Standards

These are the non-negotiable visual standards for all glyph work:

### Historical Consistency
- The reference for all design decisions is the Vatican Archives specimen and the Garamond old-style roman tradition.
- Avoid importing design patterns from unrelated typeface families (geometric sans, modern serifs, etc.).

### Contrast & Stroke Weight
- REGISTRVM is a **high-contrast** typeface. The thick/thin ratio must be preserved consistently across all new glyphs.
- New glyphs must be optically calibrated to match the existing stroke weight — do not rely on mathematical averaging.

### Serif Construction
- Serifs are **sharp and bracketed** in the classical roman manner. Avoid slab serifs, unbracketed serifs, or ball terminals.
- Serif angles and lengths must be consistent with the existing uppercase letters.

### Spacing
- Use optical spacing, not mechanical centering.
- Test spacing using the string `HOHOHO` for even color, and `AVATAR` for diagonal interactions.
- Sidebearings of symmetric letters (H, I, O, etc.) set the baseline for all other letters.

### Proportions
- REGISTRVM has **compressed proportions** relative to standard roman forms. New glyphs must not appear wider than the existing uppercase unless historically justified.

---

## Naming Conventions

Follow the [AGL (Adobe Glyph List)](https://github.com/adobe-type-tools/agl-aglfn) for standard glyph naming.

Examples:

| Character | Correct Glyph Name |
|---|---|
| A | `A` |
| À | `Agrave` |
| Á | `Aacute` |
| A (alternate) | `A.ss01` |
| fi ligature | `fi` |

Custom glyph names for non-standard forms must use a `.` suffix (e.g., `Q.swash`) to avoid Unicode conflicts.

---

## Exporting the Font

After editing, export the font from Glyphs using the following settings:

1. Open **File → Export** (or use the export panel).
2. Select **OpenType CFF (.otf)** format.
3. Set the output path to the repository root (overwrite the existing `REGISTRVM.otf`).
4. Ensure **Remove Overlap**, **Autohint**, and **Export as CFF** are checked.
5. Verify the exported file opens correctly in macOS Font Book and renders as expected.

Include the exported `REGISTRVM.otf` in your commit alongside the `.glyphs` source file.

---

## Pull Request Guidelines

A well-prepared Pull Request helps reviewers give faster, more useful feedback.

### Checklist

Before submitting, confirm:

- [ ] All changes were made in `REGISTRVM.glyphs`, not in the compiled `.otf`.
- [ ] A new `REGISTRVM.otf` has been exported and is included in the commit.
- [ ] The exported font installs and renders correctly on macOS.
- [ ] New glyphs follow the Design Standards defined above.
- [ ] Glyph names follow the AGL naming convention.
- [ ] The **Character Set table in `README.md`** has been updated to reflect any new or expanded glyph coverage.
- [ ] The commit message follows the format described above.
- [ ] Screenshots or specimen images are included for any visual change.

### What to Include in the PR Description

- **What changed:** Describe the glyphs or features added/modified.
- **Why:** Explain the design rationale, especially for interpretive choices.
- **Historical reference:** If applicable, link or reference the source material that informed the design.
- **Screenshots:** Include before/after images or a type specimen string showing the new glyphs in context. Use a dark background for high-contrast visibility.

### Review Process

Pull Requests will be reviewed by the project maintainers. Expect feedback on both the technical quality of the source file and the visual quality of the design. All visual changes require at least one approval from a maintainer before merging.

---

## Reporting Issues

Use [GitHub Issues](https://github.com/mattiacapomagi/REGISTRVM-Font/issues) to report:

- Glyph rendering errors or visual defects
- Missing Unicode mappings
- Incorrect spacing or kerning pairs
- Metric inconsistencies
- Documentation errors

When filing an issue, please include:

- **Font version** (`1.0` or the version you are testing)
- **Operating system and application** where the issue appears
- **A screenshot** clearly showing the problem
- **The string or context** that triggers the issue

---

## Code of Conduct

By participating in this project, you agree to abide by the [Code of Conduct](CODE_OF_CONDUCT.md). We are committed to maintaining a respectful and constructive environment for everyone involved.

---

*REGISTRVM is a project born from academic research and a shared passion for historical type design. We are grateful to everyone who contributes their time and skill to making it better.*
