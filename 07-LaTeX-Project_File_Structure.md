---
title: Creating a LaTeX Project File Structure
description: A best practice for a technical documentation project is to use a root file.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

A LaTeX project consists of a set of LaTeX files having a .tex extension, jpeg, png images (or other compatible formats) and stylesheets having a .sty extension.

## Using a LaTeX Root File

A User Guide or Reference Manual should, ideally, be created from multiple files, usually one file per chapter and a single root file that you would use to generate the output.

A root file is the main LaTeX file that the LaTeX typesetter uses to collect the style sheets, title page, chapters and appendices, and generate output using the defined headers and footers, TOC and so forth.

When creating a project file structure, a root file is placed in the root of the directory. All chapter .tex files, image files and stylesheets are placed in sub-directories. This allows for better file management.

To build the LaTeX document, you then need only run the build command on the root file to generate output.

## Suggested Root File Structure

The following shows the suggested structure of a documentation root file.

```latex
Root file
├── \documentclass[properties]{book}       # Use Book class
├── \usepackage{styles/stylesheet}         # Insert Stylesheet
├── \begin{document}                       # Required element
├── \frontmatter                           # Frontmatter of the Document
├── \setcounter{tocdepth}{3}               # Number of heading in TOC
├── \fancyhead[RE,LO]{}                    # Header package
├── \input{subdir/titlepage.tex}           # Input Title page (separate doc)
├── \newpage                               # Insert page break
├── \pagecolor{white}                      # Blank page in no color
├── \section*{foreward}                    # Begin forward section
├── \textbf{Document Information}          # Title of forward section
├── \begin{center}                         # Optional table, centered
├── \begin{longtable}                      # Begin the table
├── \end{longtable}                        # Close the table
├── \end{center}                           # Close the center
├── \textbf{Copyright Information}         # Add copyright info
├── \newpage                               # Insert page break
├── \tableofcontents                       # Include a TOC
├── \newpage                               # Insert page break
├── \mainmatter                            # Begin document content
├── \fancyhead[RO,LE]{\bfseries\leftmark}  # Define left header
├── \fancyhead[RE,LO]{\bfseries\rightmark} # Define right header
├── \input{subdir/chap01-preface.tex}      # Input preface from subdir
├── \input{subdir/chap02-overvew.tex}      # Input overview from subdir
├── \input{subdir/chap03-quickstart.tex}   # Input quick start from subdir
├── \input{subdir/chap04.tex}              # Input next chapter from subdir
├── \input{subdir/chap05.tex}              # Input next chapter from subdir
├── \input{subdir/chap06.tex}              # Input next chapter from subdir
├── \appendix                              # Begin Appendix
├── \input{subdir/app01-licenses.tex}      # Input appendix 1 from subdir
├── \input{subdir/app02-glossary.tex}      # Input appendix from subdir
├── \backmatter                            # Close document with backmatter
├── \end{document}                         # Indicate end of document
```
