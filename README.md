# APEX Calculus — VMI MA 124 (Calculus II)

The textbook for **MA 124, Calculus II** at VMI: the PreTeXt edition of
[*APEX Calculus*](https://www.apexcalculus.com/) by Gregory Hartman et
al., cut down to its first nine chapters: Calculus I for review, and
the Calculus II chapters the course uses, numbered as in the full book. It is published at
<https://geoff-cox.github.io/apex-ma124>, and the course site
(`geoff-cox/calc2-course`) links to it from its syllabus.

## License and attribution

*APEX Calculus* is © Gregory Hartman and licensed under the
[Creative Commons Attribution-NonCommercial 4.0 International
License](https://creativecommons.org/licenses/by-nc/4.0/). The book's
front matter carries its authors, editors, contributors and license
unchanged; keep them that way. This copy is non-commercial course
material.

## What this copy is

- **Source.** A copy of the PreTeXt sources of
  [`geoff-cox/apex-PROTEUS-fork`](https://github.com/geoff-cox/apex-PROTEUS-fork)
  at commit `5253c7f` (2026-09-29), the same way
  `geoff-cox/apex-ma123` holds the MA 123 chapters.
- **Chapters.** Chapters 1–9 of the full book, with the full book's
  numbering, so a section number in the course materials is the same as
  in any other copy of *APEX Calculus*:

  | Chapter | Title | In MA 124 |
  |---|---|---|
  | 1 | Limits | Calculus I review |
  | 2 | Derivatives | Calculus I review |
  | 3 | The Graphical Behavior of Functions | Calculus I review |
  | 4 | Applications of the Derivative | Calculus I review |
  | 5 | Integration | taught |
  | 6 | Techniques of Antidifferentiation | taught |
  | 7 | Applications of Integration | taught |
  | 8 | Differential Equations | not taught (kept to keep the numbering) |
  | 9 | Sequences and Series | taught |

  The front matter, the answers to selected exercises, the derivative
  and integral back reference and the index stay. Chapters 10–15
  (curves in the plane, vectors and the multivariable chapters) and
  their sections are removed, together with the full book's other entry
  files and publication files.
- **References into removed chapters.** One cross-reference pointed
  into a removed chapter: the closed-and-bounded aside in Section 1.5
  (continuity) referred to the multivariable "Extreme Values" section.
  It is now plain text, "Section 13.8 of the full *APEX Calculus*". No
  other text was changed.
- **Settings.** `ptx/apex-ma124.ptx` is the full book's `apex.ptx`, with
  the subtitle "VMI MA124" (the MA 123 copy has "VMI MA123") and only
  these chapters.
  `publication/publication-ma124.ptx` is the fork's `publication-web.ptx`
  with this site's base URL and issue link. The document id of the main
  version is `apex124` (the MA 123 copy uses `apex123`), so readers'
  saved work does not collide between the two books on
  `geoff-cox.github.io`.

## Building

Requires Python 3.10 or later, the PreTeXt CLI pinned in
`requirements.txt`, TeX (for the TikZ images) and Asymptote (for the 3-D
diagrams). The WeBWorK exercises are fetched from the server named in
`publication/publication-ma124.ptx` (`webwork-dev.uleth.ca`), so a full
build needs network access to it.

```
pip install -r requirements.txt
pretext build ma124       # output/ma124
pretext view ma124
```

The first build is slow: it generates every image and every WeBWorK
exercise. Runestone's services come from the copy bundled with the
pinned CLI (2.49.1 cannot parse the file Runestone's CDN serves now; the
workflow says how, and when to drop that step). `.github/workflows/deploy-pages.yml` builds the book on every
pull request and publishes it to GitHub Pages on every push to `main`
(or a manual run).

## Updating from the fork

To take later fixes from `apex-PROTEUS-fork`, copy the changed
`ptx/sec_*.ptx` and `ptx/chapter_*.ptx` files of chapters 1–9, then
re-apply the plain-text reference above (and any new one: search the
copied files for `ref="` targets that this copy does not define).
