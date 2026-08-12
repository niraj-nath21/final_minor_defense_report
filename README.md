# Minor Project — Final Report (LaTeX)

Empty skeleton following the structure of the reference report. All headings are
in place; content is left blank for you to fill in.

## Build

```bash
latexmk -pdf main.tex     # produces main.pdf
latexmk -C                # clean all build artefacts
```

## Layout

```
main.tex              <- project metadata (names, title, supervisor) + document order
preamble.tex          <- packages, geometry, heading styles, helper macros
latexmkrc             <- build config
frontmatter/
    titlepage.tex         certificate.tex     copyright.tex
    acknowledgement.tex   abstract.tex        toc.tex
    abbreviations.tex
chapters/
    ch1_introduction.tex        ch2_literature_review.tex
    ch3_methodology.tex         ch4_system_design.tex
    ch5_result_discussion.tex   ch6_conclusion.tex
backmatter/
    references.tex        appendix.tex
figures/              <- put your images here (already on \graphicspath)
```

## First steps

1. Open `main.tex` and fill in the metadata block — project title, the four member
   names and roll numbers, supervisor, HOD, external examiner, submission date.
   These feed the title page and certificate automatically.
2. Drop the college logo into `figures/` and uncomment the `\includegraphics`
   line in `frontmatter/titlepage.tex`.
3. Fill in chapter headings that are intentionally left blank (`\section{}`,
   `\subsection{}`) — these are the slots that depend on which models/modules
   your project uses.

## Figures

Every figure currently shows a grey placeholder box via `\figplaceholder`.
To insert a real image:

```latex
\begin{figure}[H]
\centering
\includegraphics[width=0.9\textwidth]{my_diagram}   % uncomment this
% \figplaceholder{7cm}{[ ... ]}                     % delete this
\caption{My Diagram}
\label{fig:my-diagram}
\end{figure}
```

Images are looked up in `figures/` and `figures/placeholders/`, so no path prefix
is needed.

## Chapter 4 diagrams

Nine diagram slots, in this order:

| § | Diagram |
|---|---|
| 4.2 | Context Diagram |
| 4.3.1 | DFD Level 0 |
| 4.3.2 | DFD Level 1 |
| 4.4 | Use Case Diagram |
| 4.5 | Class Diagram |
| 4.6 | Sequence Diagram |
| 4.7 | Component Diagram |
| 4.8 | Deployment Diagram |
| 4.9 | Gantt Chart |

The Gantt chart has two options in `ch4_system_design.tex`: paste an exported
image, or fill in the `pgfgantt` skeleton (one `\ganttbar{name}{start}{end}` per
task). The pgfgantt version is active by default.

## Conventions carried over from the reference report

- A4, 12pt, Latin Modern, one-half line spacing.
- Chapters open as `CHAPTER N` with the title in caps beneath.
- Headings numbered to 5 levels — use `\paragraph{}` for level 4 (e.g. 5.1.1.1.1)
  and `\subparagraph{}` for level 5.
- Front matter in roman numerals starting at the Copyright page (i); title page
  and certificate are unnumbered.
- Figures numbered per chapter, all auto-listed in *List of Figures*.
- IEEE numeric citations via `thebibliography` in `backmatter/references.tex` —
  add a `\bibitem{key}` per source and cite with `\cite{key}`.
- The reference report has no *List of Tables*; one is included here since the
  skeleton has numbered tables. Delete the marked block in `frontmatter/toc.tex`
  if you don't want it.
