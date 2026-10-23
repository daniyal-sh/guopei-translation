# Translation and typesetting guide

You are translating a Chinese physics-olympiad textbook into English and typesetting it in LaTeX.
The result must read like a serious physics textbook, not like a machine translation.

## Absolute requirements

1. **Translate everything** on every assigned page: prose, problem statements, hints, solutions,
   captions, table entries, figure labels, footnotes. Do not summarise, abridge, or add material.
2. **Keep the original numbering** of problems, equations, figures and parts exactly
   (Problem 1.09, equation (3), Fig. 1.09, part (2), etc.).
3. **Recreate every figure** as a TikZ drawing inside the assigned `.tex` file.
   Do not include scanned images. Do not omit a figure. Schematic line drawings are expected;
   they must be clear, correctly labelled, and consistent with the text.
4. **All mathematics must be typeset in LaTeX.** Never write ASCII substitutes such as `v0^2`
   or `sqrt(...)` in the running text.
5. Write only English in the output. No Chinese characters may remain.
6. The page images are the authority. The OCR text files are a rough aid and contain errors;
   always check the image for symbols, subscripts, signs and figure labels.

## Inputs

Page images: `pages/pNNN.png` (NNN = three-digit PDF page number, e.g. `pages/p023.png`).
OCR text: `ocr/pNNN.txt` (UTF-8, may contain recognition errors).
Work through the pages in order. Read the image of each page before translating it.

## Output

Write the assigned file (given in the task) as a fragment only:
no `\documentclass`, no preamble, no `\begin{document}`, no `\chapter`, no `\end{document}`.
The master file supplies the preamble and the chapter structure.

Environments available (defined in `book/preamble.tex`):

```latex
\begin{problem}{1.09} ... \end{problem}
\begin{hint}{1.09} ... \end{hint}
\begin{solution}{1.09} ... \end{solution}
\begin{note} ... \end{note}          % for a short editorial note, if the original has one
\begin{commentary} ... \end{commentary} % for 【点评】 at the end of a solution
\begin{figbox}{1.09}
\begin{tikzpicture} ... \end{tikzpicture}
\end{figbox}
```

`figbox` prints "Fig. 1.09" underneath. For several figures belonging to one problem use
`{1.09(a)}`, `{1.09(b)}`, etc.

Use `\section{...}` only when the task explicitly asks for it; otherwise the file is included
under an existing section.

## Mathematical style

- Vectors: `\vec{v}`, `\vec{F}`. Unit vectors: `\hat{x}`, `\hat{r}`.
- Differential: `\dd x`, `\dd t` (macro `\dd` is defined). Exponential: `\ee^x`, imaginary `\ii`.
- Units upright: `9.8\unitv{m/s^2}` or `\SI{9.8}{m/s^2}`. Degrees: `30\degree`.
- Numbered equations exactly as in the original:
  `\begin{equation}\tag{1} ... \end{equation}`.
  Refer to them in the text as `(1)`, not with `\eqref`, so that the numbering is preserved
  even when an equation is repeated.
- Multi-line derivations: `\begin{align} ... \end{align}` with `\tag{n}` on the lines that are
  numbered in the original. Do not number lines that are unnumbered in the original.
- Use `\dfrac` in display mathematics, `\frac` in inline mathematics.
- Do not invent equation numbers.

## Figures

- Draw with TikZ (`tikzpicture`), line width about 0.5 pt, arrows `->` or the `force` style.
- Use the styles defined in the preamble: `thickline`, `dashedline`, `axis`, `force`, `dim`,
  `hatch`, `ball`, `mass`, `spring`.
- Label points with italic math: `node[below] {$A$}`. Label lengths with `dim` arrows.
- Keep a figure at most about 9 cm wide and 6 cm high unless the original is larger.
- Every symbol used in the figure must be explained in the text or caption, as in the original.
- For experimental apparatus, draw a clean schematic view; for circuit diagrams use ordinary
  TikZ circuit symbols (battery, resistor, capacitor, coil, ammeter, voltmeter).
- Do not use external image files.

## Language

- Formal, precise textbook English. Prefer short sentences. Keep the logical connectives
  ("hence", "therefore", "it follows that") of the original.
- Translate physical terms consistently: 质点 particle, 刚体 rigid body, 光滑 smooth/frictionless,
  轻杆 light rod, 细绳 string, 弹簧 spring, 斜面 inclined plane, 碰撞 collision,
  动量 momentum, 角动量 angular momentum, 质心 centre of mass, 转动惯量 moment of inertia,
  简谐振动 simple harmonic motion, 电场 electric field, 电势 potential, 电容 capacitance,
  电感 inductance, 磁感应强度 magnetic flux density, 折射率 refractive index,
  焦距 focal length, 干涉 interference, 衍射 diffraction, 偏振 polarisation,
  光子 photon, 能级 energy level, 结合能 binding energy, 半衰期 half-life.
- Keep symbols in mathematics unchanged (do not translate $m$, $v$, $\omega$).
- "题解" = Solution; "提示" = Hint; "点评" = Comment; "解" = Solution;
  "试求/求" = find/determine; "如图所示" = as shown in the figure.

## Procedure

1. Read the assigned pages in order (image + OCR).
2. Write the LaTeX fragment to the assigned path with the `write` tool.
3. For long assignments, write the file in several successive parts (write the first part,
   then append with `edit` by replacing a unique final line, or use a small Python append),
   so that no single response becomes too long. Never leave a page untranslated.
4. After writing, re-read your file and check: every problem number present, every figure
   present, braces and environments balanced, no Chinese characters, no raw Unicode symbols.
5. Compile-check is not required (the master file does it), but the fragment must be valid
   LaTeX on its own apart from the preamble.
6. End with a short report: pages covered, problem numbers covered, figures drawn,
   any illegible passage or missing page.

Do not modify any file other than the one assigned to you.
