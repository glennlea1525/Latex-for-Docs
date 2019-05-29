---
title: Adding Font Selection Support and Defining Fonts
description: Define the base font for your document and font support for monospaced font and font size specifications.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

Setting fonts in LaTeX is not an obvious task. It is, to be honest, rather cumbersome. I should start with the basis.

## Basic Font Commands

You need to add font declarations that are valid during the current scope in the document.

A roman font family is added using the following:

```latex
\rmfamily
```

A sans serif font is added using the following:

```latex
\sffamily
```

A monospaced font is added using the following:

```latex
\ttfamily
```

You can then add the following declarations within each font family by using the following:

```latex
\mdseries   % formats the font as regular, well, actually it keeps the font as is.
\bfseries   % makes the font Bold.
```

Text strings can be formatted using the following:

```latex
\upshate  % reverts the text back to normal
\slshape  % forward slants the text
\itshape  % italicizes the font
\scshape  % makes the text All Caps and Small Caps
```

## Setting Base Fonts
For my documentation, I wanted to use several fonts. I used Helvetica for the base font and Latin Modern as an alternate base font. Latin Modern is a set of true handmade vector fonts.

In the stylesheet, I added the following commands. The first two set the base fonts for the document. The third command changes the default family to Sans Serif

```latex
\usepackage{lmodern}  % Alternate base font
\usepackage{helvet}   % Base font for document
\renewcommand{\familydefault}{\sfdefault}  % Changes the default family to Sans Serif
```

Adding the mic

To improve readability, the microtype package is added. If it is used, options and settings need to be made. The PostScript font Adobe Courier is used for monospace text.

    \usepackage{microtype}
    \usepackage{courier}


To allow relative font size specifications, (e.g. \smaller, \larger) the package relsize is used.

    \usepackage{relsize}


To control the fonts and formatting used in the table of contents, use the titles package and set the argument tocloft.

    \usepackage[titles]{tocloft}


You can redefine the spacing to make the text more aesthetically appealing.

    \setlength{\cftbeforechapskip}{2ex}
    \setlength{\cftbeforesecskip}{0.5ex}


Finally, you can create a courier text style and a default paragraph text style that can be applied as needed.

    \newcommand\textstyleCourier[1]{\texttt{#1}}
    \newcommand\textstyleDefaultParagraphFont[1]{#1}
    \makeatletter
    \newcommand\arraybslash{\let\@arraycr}
    \makeatother


Dummy text is available with the lipsum package.

    \usepackage{lipsum}
