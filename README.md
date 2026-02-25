# bioarxiv-quarto

Quarto Typst-based PDF format extension for producing bioRxiv-style preprint PDFs.

[View example PDF](https://chi-raag.github.io/bioarxiv-quarto/template.pdf)

Requires **Quarto >= 1.8.0**.

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

## Format Options

Key YAML options accepted by `bioarxiv-typst`:

| Option | Level | Description |
|---|---|---|
| `title` | top | Manuscript title |
| `shorttitle` | top | Short title for the running header (defaults to `title`) |
| `leadauthor` | top | Last name shown in the footer (defaults to first author's surname) |
| `author` | top | List of authors with `name`, `affiliations`, `email`, `corresponding` |
| `abstract` | top | Abstract text |
| `keywords` | top | List of keywords |
| `correspondence-email` | top | Email shown in the correspondence footnote |
| `bibliography` | top | Path to a `.bib` file |
| `bibliographystyle` | format | Typst citation style (default: `springer-basic`) |
| `columns` | format | Number of columns: `1` or `2` (default: `2`) |

### Author / affiliation syntax

```yaml
author:
  - name: John Doe
    corresponding: true
    affiliations:
      - Department of X, University Y, City, Country
    email: john.doe@example.org
```

Affiliations can be plain strings (as above) or structured maps with `name`, `department`, `city`, `country`, etc.

## Citations (Typst)

This format uses Typst's built-in citation system by default.

- Default style: `bibliographystyle: springer-basic` (Typst built-in).
- Override with a Typst built-in style (e.g. `bibliographystyle: apa`) or an
  independent `.csl` file path.

If you prefer Pandoc citeproc instead, set `citeproc: true` and use `csl:` (path
or URL).

## Fonts

The template uses **Libertinus Serif** for body text. If Libertinus Serif is not
installed, it falls back to **New Computer Modern**. Both are freely available.

## Attribution

This format is inspired by two wonderful projects:

- [Henriques Lab bioRxiv LaTeX template](https://www.overleaf.com/latex/templates/henriqueslab-biorxiv-template/nyprsybwffws)
- [quarto-preprint](https://github.com/mvuorre/quarto-preprint)
