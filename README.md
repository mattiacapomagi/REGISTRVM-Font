# REGISTRVM

![Version](https://img.shields.io/badge/version-1.0-c8a96e?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-c8a96e?style=flat-square)
![Status](https://img.shields.io/badge/status-early%20release-8c7a5e?style=flat-square)

REGISTRVM is an open-source Renaissance-inspired display typeface developed as a university project for the Type Design course at **RUFA – Rome University of Fine Arts** by Mattia Capomagi and Leonardo Borri, under the supervision of teacher and type designer Antonio Pace.

---

## Background

The typeface is not a design drawn entirely from scratch. It is a **typographic revival** grounded in a specific historical specimen from the Vatican Archives — an inscription typeset in a monumental roman style characteristic of the late Renaissance and early Baroque periods. Additional influence comes from Garamond-style old-style roman forms, particularly in the construction of serifs, stroke modulation, and proportional relationships between letters.

The name *REGISTRVM* (Latin: *registrum*, a formal record or ledger) reflects both the institutional gravity of the source material and the project's academic origins.

The project is still in an early stage. The current font is intended for **titles, inscriptions, short display text, and historical or editorial layouts** where a classical roman atmosphere is appropriate. It is not suitable for body text at small sizes.

---

## Design Characteristics

REGISTRVM inherits the following formal qualities from its historical source:

- **High stroke contrast** — strong thick/thin differentiation between vertical stems and horizontal hairlines
- **Compressed proportions** — letters are narrower than standard roman forms, closer to epigraphic tradition than text typography
- **Sharp bracketed serifs** — classical wedge serifs with minimal bracketing, giving the typeface a lapidary, carved quality
- **Optical weight** — the design is calibrated for large-scale display, where fine details in the serifs and stroke endings remain legible
- **Monumental register** — best suited for all-caps settings, headlines, and formal contexts

---


## Character Set

The current version covers:

| Category | Detail |
|---|---|
| Basic Latin capitals | `A–Z` (26 glyphs) |
| Accented capitals | Acute and grave variants for `À Á È É Ì Í Ò Ó Ù Ú` |
| Punctuation | `.` `,` `:` `;` `!` `?` `"` `'` `/` `\` `-` `_` `*` `&` |
| Stylistic alternates | Selected letters with historical alternate forms (`ss01`) |
| Lowercase mapping | Lowercase Unicode codepoints currently map to the uppercase forms |

> **Note on lowercase:** The font does not yet include a dedicated lowercase design. All lowercase Unicode characters render as their uppercase equivalents. This is a known limitation and the highest-priority area for future development.

---

## Technical Specifications

| Property | Value |
|---|---|
| Units Per Em (UPM) | 1000 |
| Format | OpenType CFF |
| OpenType features | `ss01` (stylistic alternates) |
| Hinting | Autohinted via Glyphs export |
| Encoding | Unicode |

---

## Roadmap

The following areas are planned or under consideration for future versions:

- [ ] **Lowercase set** — historically informed old-style roman lowercase `a–z`
- [ ] **Numerals** — oldstyle figures `0–9`
- [ ] **Expanded accented Latin** — broader language support beyond current acute/grave coverage
- [ ] **Kerning** — systematic optical kerning pairs
- [ ] **Spacing refinement** — full sidebearing review
- [ ] **Additional stylistic alternates** — more historical variant forms
- [ ] **Small capitals** — true small caps for use in mixed-case settings
- [ ] **Bold weight** — a heavier variant, optically corrected (not mechanically interpolated)

Contributions toward any of these milestones are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full workflow.

---

## Installation

Download `REGISTRVM.otf` from the repository and install it through your operating system's font manager.

**macOS:** Double-click the file and choose **Install** in Font Book.  
**Windows:** Right-click the file and choose **Install** or **Install for all users**.  
**Linux:** Copy the file to `~/.local/share/fonts/` and run `fc-cache -f`.

Once installed, the font is available in any application under the name **REGISTRVM**.

---

## Usage Recommendations

- **Minimum size:** 18pt or equivalent for print; 24px for screen display
- **Ideal use cases:** Book covers, chapter headings, editorial titles, posters, inscriptions, exhibition labels, historical publications
- **Avoid:** Body text, captions, UI labels, digital interfaces requiring legibility at small sizes
- **All-caps setting:** REGISTRVM is designed primarily for all-caps typesetting. Mixed-case output (until a true lowercase is added) may produce visually uneven results depending on the application
- **Tracking:** Light positive tracking (+20 to +80 in most applications) generally improves legibility and suits the monumental register of the typeface

---

## Source & Modification

The editable source is `REGISTRVM.glyphs`, designed to be opened in **Glyphs 3**. If you want to study, modify, or extend the typeface, always start from the source file rather than editing the compiled `.otf` directly.

The `.otf` in this repository is a **build artifact** and will be overwritten on each release. It is included for direct use by those who do not need to edit the source.

---

## Contributing

REGISTRVM is open source so that designers, typographers, and researchers can study it, improve it, and build on it. Contributions of all kinds are welcome — from new glyphs and spacing work to documentation and testing.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting changes. It covers the full workflow, design standards, naming conventions, and PR guidelines.

---

## License

REGISTRVM is released under the **MIT License**. See [LICENSE](LICENSE) for details.

You are free to use, modify, and distribute the font — including in commercial projects — as long as the original copyright notice is retained.

---

## Credits

**Type Design:** Mattia Capomagi, Leonardo Borri  
**Academic Supervision:** Antonio Pace (type designer, RUFA)  
**Institution:** RUFA – Rome University of Fine Arts, Type Design course  
**Historical Source:** Vatican Archives specimen (late Renaissance roman inscription)  
**Tools:** [Glyphs 3](https://glyphsapp.com/)
