# RoboCasa Paper Draft — IROS 2027

LaTeX sources for an IROS 2027 submission on the RoboCasa experiments: surveying the success conditions RoboCasa tasks state, representing them (and RoboCasa's admissible regions) as random events, and measuring what that representation costs and captures.

The experiment code lives in `experiments/src/experiments/random_events_experiments/` of the CRAM repository.

## Layout

- [paper/main.tex](paper/main.tex) — paper source (IEEE conference format, `ieeeconf.cls`)
- [paper/references.bib](paper/references.bib) — bibliography
- [paper/figures/](paper/figures/) — figures
- [paper/ieeeconf.cls](paper/ieeeconf.cls), [paper/IEEEtran.bst](paper/IEEEtran.bst) — IROS style files
- [iros_template/](iros_template/) — the unmodified IROS/PaperCept `ieeeconf` template, kept for reference

IROS allows 6 pages plus up to 2 additional (paid) pages, references included. Draft notes are written with `\todo{...}` and `\note{who}{...}`; switch `\drafttrue` to `\draftfalse` in `main.tex` to hide them.

## Building locally

Requires a TeX Live installation with `latexmk`:

```bash
cd paper
latexmk -pdf main.tex
```

## Continuous integration

[.github/workflows/build-paper.yml](.github/workflows/build-paper.yml) compiles `paper/main.tex` on every push and pull request and uploads the resulting PDF as a build artifact (`paper-pdf`). On pushes to `main` it also publishes the PDF to GitHub Pages.

Once Pages is enabled (Settings → Pages → Source: "GitHub Actions"), the compiled paper is available, up to date with `main`, at `https://<user>.github.io/<repo>/`.
