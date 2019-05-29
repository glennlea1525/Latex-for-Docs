---
title: Setting Page Size, Margins and Layout
description: Before customizing headers and footers, you should define the page size, margins and layout.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

Before you begin defining headers and footers and adding content to chapters, you need to set up the document page size, page margins and page layout.

## Setting Page Size

For defining all text/page measurements, 210mm x 295mm is the standard A4 page size. You can also use letterpaper for US letter size.

You define the page size using the `\documentclass` command in the root file.

```latex
\documentclass[a4paper,11pt,twoside]{book}
```
This sets the page size, the base font size (11 pt) and pagination (double-sided).

## Defining Margin Layout

Margins are defined in the stylesheet using the following commands.

```latex
\usepackage[vcentering,dvips]{geometry}
\geometry{papersize={210mm,295mm},total={160mm,185mm}}
```

The `geometry` package has two arguments:

  * `vcentering` which sets auto-centering vertically and is equivelant to marginration=1:1.
  * `dvips` which writes the paper size in the dvi output.

The dvips option will be superceded if pdflatex is used, but is necessary to generate a correct PostScript bounding box under standard LaTeX.

The `\geometry` command sets the `papersize` precisely, where

  * `papersize` determines the size of the paper, which in this case is 210mm by 295mm.
  * `total` defines the dimensions of the text body or content area of the document, which is 160mm x 185mm. This results in pleasing margins.

## Defining Offsets for Headers and Footers

This package is used to define the offsets for headers and footers. If you want to just copy my settings, please feel free to go ahead. The following is the page layout for an A4 page size.

Set the left, right, top margins and mirror the margins for double-sided pages.

```latex
\setlength\voffset{-1in}
\setlength\hoffset{-1in}
\setlength\topmargin{1cm}
\setlength\oddsidemargin{3cm}
\setlength{\evensidemargin}{3cm}
```

The height of the text flow on each page is defined using this command.

```latex
\setlength\textheight{23.5cm}
```

The width of the text flow is defined using these commands. `footskip` defines the distance between the footer and body text. Take care when modifying these settings.

```latex
% Set text width
\setlength\textwidth{15cm}
% Set distance between footer and body text
\setlength\footskip{1.0cm}
% Set the header height
\setlength\headheight{1cm}
\setlength\headsep{1cm}
% Set the footer height and distance between footer and text body.
%\setlength\footheight{1cm} % Unused
% \setlength\footsep{1cm} % Unused
% Indent the paragraph to 0cm, that is, do not have an indentation on the first line.
\setlength{\parindent}{0cm}
% Paragraph spacing is determined by `\parskip`, which is in this case 3 pts.
\setlength{\parskip}{3pt}
```

## Line Spacing

Line spacing is determined by three commands. In the following example, line spacing is set to 1.5 using the `\setspace` package.

```latex
\usepackage{setspace}
\singlespacing

%\onehalfspacing
%\doublespacing

\setstretch{1.1}
```

Alternately, you can use the command `\baselinestretch` but you must adjust the command as follows:

    \renewcommand{\baselinestretch}{1.5}

**Note:** The `\renewcommand{}` redefines a command.
{: .notice--info}
