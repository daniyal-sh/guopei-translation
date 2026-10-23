# Training and Selection for the International Physics Olympiad

English LaTeX edition of Zheng Yongling (郑永令), *国际物理奥赛的培训与选拔*
(*Guoji Wuli Aosai de Peixun yu Xuanba*), Fudan University Press.

The book contains:

- **Problems** — 190 problems in mechanics, thermodynamics, electromagnetism, optics and atomic physics
- **Hints** — 197 hints
- **Solutions** — full worked solutions, including alternative methods and commentary
- **Experiments** — 80 experimental problems with apparatus, procedures, data tables and analysis
- **Appendix A** — the IPhO syllabus and the 31st–34th International Physics Olympiad problems and solutions
- **Appendix B** — physical constants, astronomical data and mathematical formulas

All figures are original vector TikZ drawings; every problem, hint, solution, table and
numerical value from the available source pages is reproduced.

## Credits

- Original Chinese edition: edited by **Zheng Yongling**, Fudan University Press
- English translation and typesetting: **Daniyal Shahzad Hamid**, with **DeepSeek V4.1 Flash**

## Build

Requires a TeX distribution with TikZ, pgfplots, booktabs, siunitx and the standard
LaTeX packages.

```bash
cd book
pdflatex main.tex
pdflatex main.tex
```

The compiled book is also provided as
`dist/Training_and_Selection_for_the_International_Physics_Olympiad.pdf` (632 pages).

## A note on the source

The scanned Chinese original used for this translation is defective in a few places:
several pages are missing or cut off. Those passages are marked with short notes in the
book rather than filled with invented text. The IPhO syllabus section was restored from
the official syllabus.

Rights to the original Chinese text remain with Fudan University Press and the original
authors. This repository is a non-commercial translation prepared for study and reference.
