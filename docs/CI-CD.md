# GitHub Actions CI/CD for LaTeX Thesis

This document explains the automated compilation system for the LaTeX thesis.

## Overview

The GitHub Actions workflow automatically compiles the LaTeX document in the `primer-impresion` folder whenever changes are pushed to the main branch or when pull requests are created.

## Workflow Details

### File Location
- `.github/workflows/latex-compile.yml`

### Triggers
- Push to `main` branch
- Pull requests targeting `main` branch

### Compilation Process

1. **Environment Setup**
   - Ubuntu latest runner
   - Full TeX Live installation
   - Spanish language support
   - All required LaTeX packages

2. **Required Packages**
   - `texlive-latex-base` - Core LaTeX
   - `texlive-latex-recommended` - Common packages
   - `texlive-latex-extra` - Additional packages
   - `texlive-fonts-recommended` - Font support
   - `texlive-fonts-extra` - Extended fonts (including Arimo)
   - `texlive-lang-spanish` - Spanish language support
   - `texlive-bibtex-extra` - Bibliography tools
   - `texlive-pictures` - Graphics and diagrams
   - `texlive-science` - Mathematical and scientific packages
   - `biber` - Bibliography processor
   - `latexmk` - LaTeX build tool
   - `make` - Build automation

3. **Compilation Steps**
   ```bash
   cd primer-impresion
   make build
   ```
   
   This executes:
   ```bash
   pdflatex mydocument.tex
   biber mydocument
   pdflatex mydocument.tex
   pdflatex mydocument.tex
   ```

4. **Output**
   - Generated PDF is uploaded as an artifact
   - Artifact name: `thesis-pdf`
   - Retention: 30 days
   - File: `primer-impresion/mydocument.pdf`

## Supported Features

The compilation supports all thesis requirements:

### Document Features
- **Font**: Arimo (San Francisco style)
- **Language**: Spanish with proper hyphenation
- **Bibliography**: Vancouver style with Biber
- **Images**: PNG, PDF inclusion
- **Tables**: Complex tables with tabularray
- **Mathematics**: Full AMS math support
- **Links**: Hyperref with hidden borders

### Input Files
- `mydocument.tex` - Main LaTeX file
- `mydocument.bib` - Bibliography database
- `extras/` - PDF attachments (cover pages, permits, etc.)
- `images/` - Figures and images

## Viewing Results

1. Go to the [Actions tab](https://github.com/dxnst/tesis-latex/actions)
2. Click on the latest workflow run
3. Download the `thesis-pdf` artifact
4. Extract and view `mydocument.pdf`

## Local Development

For local development, ensure you have:
- TeX Live (full installation recommended)
- Biber for bibliography processing
- Make for build automation

Then run:
```bash
cd primer-impresion
make build
```

## Troubleshooting

### Common Issues
1. **Missing packages**: The workflow installs comprehensive LaTeX packages
2. **Bibliography errors**: Biber handles UTF-8 and special characters properly
3. **Font issues**: Arimo font is included in `texlive-fonts-extra`
4. **PDF version warnings**: These are warnings only and don't prevent compilation

### Log Access
- View detailed compilation logs in the GitHub Actions run
- Check for any warning messages or errors
- PDF file size is displayed for verification

## Technical Notes

- Compilation typically takes 3-5 minutes
- Final PDF is approximately 6.8MB (128 pages)
- Supports Spanish characters and accents
- Handles complex bibliography with 100+ references
- Includes multiple embedded PDFs and images