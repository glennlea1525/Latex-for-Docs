---
title: Structuring a LaTeX Root File
description: This topic provides a simplified root file.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}
A root file in LaTeX gives the document its structure. The title page, stylesheets, table of contents, chapters, and appendices are references in the root file using `\include` commands.

## Root File Sections
The following is a simplified root file.

```latex
\documentclass[a4paper,12pt,draft,twoside]{book}
\usepackage{styles/mystyles}
\begin{document}
\frontmatter
\include{tex/title}
\tableofcontents
\mainmatter
\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}
\backmatter
\end{document}
```

let's go through this file section by section.

### 1. Defining the Document Class

The first line tells the LaTeX generator the type of document it is about to generate (or typeset) and what styles are to be used.

```latex
    \documentclass[a4paper,12pt,draft,twoside]{book}
```

All these elements are defined in separate class files. More about these classes later.

The \documentclass line defines the type of document you intend to create. This document will be printed (or output to pdf) in A4 format. The base font will be 12 points, although this can be modified in the document. It is marked as draft initially. And it will be printed on both sides.

The word *book* within the curly braces tells the typesetter to use the Book class. This is a set of predefined outputting instructions, which in this case has functionality that can handle large multi-chapter documents, which manuals tend to be.

**Note:** Another option is using the *memoir* class, which offers a useful alternative.
{: .notice}

### 2. Referencing the Stylesheet

Following the document class definition, you tell the typesetting engine to use the styles defined in an external document called *mystyles* which is located in a directory below the root called *styles*.

```latex
    \usepackage{styles/mystyles}
```

*mystyles* is a stylesheet where all the styles have been defined that will be used in this document. This allows me to update the stylesheet without having to worry about finding the styles within the root file (which is the alternate location for styles).

### 3. Beginning the Document Scope

Like the body tag in HTML, the actual content follows this tag:

```latex
    \begin{document}
```

This command tells the typesetter that what follows is the document. The document section is divided into three sections: *frontmatter*, *mainmatter* and *backmatter*.

### 4. Defining a Title Page

Within the **frontmatter** section, I included a title page, although the book class has a default title page which can be referred to simply as **titlepage**. In this section I want my table of contents as well, which is automatically generated during output.

```latex
    \frontmatter
    \include{tex/title}
    \tableofcontents
```

### 5. Including the Document Content

The document itself, namely, the contents, is contained within the *mainmatter* section.

```latex
    \mainmatter
```

To keep this simple and to allow chapters to be toggled off or on (included/excluded) as required, all content is placed in external files in a subdirectory called *tex*.

The \include command is used to tell the typesetter to locate the file referenced within the curly braces and include it in the output stream at the location in the list of includes.

```latex
    \include{tex/preface}
    \include{tex/intro}
    \include{tex/chap01}
    \include{tex/chap02}
    \include{tex/summary}
```

**Note:** You would also define your headers and footers here, but I excluded them in this example to keep it simple. I will get to them in due time. I also included an appendix, but is not shown in my example.
{: .notice}

A *backmatter* section is also included, which typically includes the Index.

```latex
    \backmatter
```

### 6. Ending the Document Scope

You need to tell the typesetter when the document is complete, that is, there is no more files to generate. In other words, you need to close your document, as in all tagged files.

```latex
    \end{document}
```

This simple command indicates the end of the document and go ahead and generate the output.

## Sample Manual Root File

Here is a sample manual root file that you can use right away to get you started. I will go through the sections in upcoming topics.

```latex

% Copyright 2017 Glenn J. Lea
% Manual ROOT FILE % MAIN FILE
%\RequirePackage[l2tabu, orthodox]{nag}
\documentclass[a4paper,11pt,twoside]{book}
% INSERT styles-template.sty
\usepackage{styles/template}
\begin{document}
\frontmatter
%% Configuration of the header strings for the frontmatter pages.
\setcounter{tocdepth}{3}
\fancyhead[RE,LO]{}
% Document Title Page
\input{MANUAL/manual-titlepage.tex}
%\thispagestyle{empty}
\newpage
\pagecolor{white}
% Forward Section  
% \section*{Foreward}
\textbf{{Document Information}}  
\begin{center}
\begin{longtable}{&gt;{\RaggedLeft}p{4cm}|&gt;{\RaggedRight}p{10cm}}
\endfirsthead \multicolumn{2}{l}{\textit{Document Information continued}}\
\endhead \multicolumn{2}{r}{\textit{Continued on next page}}\
\endfoot
\endlastfoot
\textbf{Item} &amp; \textbf{Description}
\Document Version &amp; Version #\\
Revision Number &amp; Rev #\\
Document ID #\
Date Published #\
\end{longtable}
\end{center}
% Copyright Information
\textbf{{Copyright Information}}
\textbf{Glenn J.Lea}\\
\textbf{Additional Information}\
\newpage
% Table of Contents %
\tableofcontents
\newpage  
% Body of the Document
\mainmatter{}
% Configuration of the header strings for the main pages.
%\fancyhead[RE,LO]{\thesection}
\fancyhead[RO,LE]{\bfseries\leftmark}
\fancyhead[RE,LO]{\bfseries\rightmark}
%% Chapters inputs
\input{MANUAL/manual-ch01-preface.tex}
\input{MANUAL/manual-ch02-overvew.tex}
\input{MANUAL/manual-ch03.tex}
\input{MANUAL/manual-ch04.tex}
\input{MANUAL/manual-ch05.tex}
%% Appendix Inputs
\appendix
\input{MANUAL/app01.tex}
\input{MANUAL/app02.tex}
\input{MANUAL/app05-glossary.tex}
\backmatter
\end{document}
```    
