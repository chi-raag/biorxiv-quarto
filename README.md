# bioarxiv-quarto

Quarto Typst-based PDF format extension for producing bioRxiv-style preprint PDFs.

The PDF format is implemented as a Quarto extension in `_extensions/bioarxiv/`
and provides the output format `bioarxiv-typst` (PDF output).

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
columns: 1

format:
  bioarxiv-typst: {}
```

Or format-scoped:

```yaml
format:
  bioarxiv-typst:
    columns: 1
```

## Attribution and licensing

This format is inspired by the Henriques Lab bioRxiv LaTeX template but does
not bundle their LaTeX class/BibTeX assets. See `_extensions/bioarxiv/NOTICE.md`.
