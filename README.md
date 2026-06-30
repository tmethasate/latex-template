# LaTeX Template Collection

Reusable LaTeX templates for letters, research proposals, and small document
utilities.

## Templates

| Path | Purpose | Main file |
| --- | --- | --- |
| `Cover Letter/Formal Letter_Template.tex` | Thin formal letter template with a traditional `letter` layout. | `Formal Letter_Template.tex` |
| `Cover Letter/Plain Cover Letter_Template.tex` | Plain cover letter template with sender and recipient blocks. | `Plain Cover Letter_Template.tex` |
| `Cover Letter/Simple Cover Letter/` | Modular cover letter with personal details and body text split into separate files. | `main.tex` |
| `Official Letter/Ministry of Commerce Data Request Letter/` | Thai official data-request letter based on the Ministry of Commerce request. Includes local TH Sarabun New fonts, bibliography data, and `example.pdf`. | `m_commerce_data_request_letter.tex` |
| `Research Proposal/` | Multi-section research proposal template with bibliography support. | `main.tex` |
| `Wordcount (Verbatim)/` | Example for displaying a `texcount` word count inside a document. | `main.tex` |

## Building

Most templates can be compiled with a standard LaTeX workflow, for example:

```sh
latexmk -pdf main.tex
```

The Thai official-letter template uses `fontspec`, Thai line breaking, and
`biblatex`, so build it with XeLaTeX and Biber:

```sh
cd "Official Letter/Ministry of Commerce Data Request Letter"
latexmk -xelatex m_commerce_data_request_letter.tex
```

If `latexmk` is not available, run `xelatex`, `biber`, and `xelatex` again on
`m_commerce_data_request_letter.tex`.

The word-count example uses `\write18`, so it requires shell escape and
`texcount`:

```sh
pdflatex -shell-escape main.tex
```

## Notes

- Generated LaTeX build files are ignored; PDFs are kept trackable because they
  are useful previews for templates.
- Some imported templates contain their own license headers. Check those headers
  before reusing or redistributing a specific template.
