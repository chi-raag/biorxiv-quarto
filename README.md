# bioarxiv-quarto

Quarto Typst-based PDF format extension for producing bioRxiv-style preprint PDFs.

## Use as a template (new manuscript)

```bash
quarto use template chi-raag/bioarxiv-quarto
```

## Install into an existing project

```bash
quarto add chi-raag/bioarxiv-quarto
```

## Render

```bash
quarto render template.qmd --to bioarxiv-typst
```

## Citations (CSL)

Typst requires an **independent** CSL file (dependent CSL styles aren’t
supported). This extension defaults to
`oxford-journals-scimed-author-date.csl` (the independent
parent of Zotero’s dependent `bioinformatics` style).

Override per-document by setting `csl:` to a local `.csl` file path.

## Columns

The format defaults to two-column layout. Override per-document with:

```yaml
format:
  bioarxiv-typst:
    columns: 1
```

## Attribution

This format is inspired by two wonderful projects:

- [Henriques Lab bioRxiv LaTeX template](https://www.overleaf.com/latex/templates/henriqueslab-biorxiv-template/nyprsybwffws)
- [quarto-preprint](https://github.com/mvuorre/quarto-preprint)
