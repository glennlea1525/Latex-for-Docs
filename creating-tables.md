# Creating Tables

You can add simple to complex tables to a LaTeX document using several types of packages, depending on the requirements of the table.

As befits a technology designed for academia and scientific research, LaTeX provides a wide range of table options. I don't assume all knowledge when it comes to creating tables in LaTeX but I provide a few ideas or samples you can use.

A consultant working with my client came up with some very cool customized table environments which showed me what is possible. He created macros in a stylesheet which he then simply applied to a table in a document for quick formatting. If you can do this sort of LaTeX wizardry, then this is the way to go.

Nevertheless, for the sake of completness, here are some simple examples you can start with to add tables to your document.

## Table Packages

LaTeX provides several packages for adding tables to a LaTeX document. You can use the `tabular` package, the `tabularx` package or the `supertabular` package, amongst others.

An `array` package is available to typeset cell contents in math mode. When using `tabular`, `tabularx` or `supertabular`, the cell contents are in text mode.

## A Basic Table

You can insert a basic table using the `tabular` environment.

```latex
\begin{center}
\begin{tabular}{|l|l|l|}
Column Heading & Column Heading & Column Heading \\\
\hline
Cell contents & Cell contents & Cell contents \\
Cell contents & Cell contents & Cell contents \\
Cell contents & Cell contents & Cell contents \\
\end{tabular}
\end{center}
```

The line `\begin{tabular}{|l|l|l|}` creates a table with three columns that are left aligned and have a vertical line between each column.

Next, column headings are added where each heading is marked off by a `&` symbol and where the row is ended with the command `\\`.

A horizontal line is added using `\hline`.

The cell contents follow the same structure as column headings.

## Using the supertabular Package

I added the following commands to my stylesheet to use the `supertabular` package. The additional commands allowed me to create more complex tables.

```latex
% Table-related Styles and Packages
% Package for making supertabular tables
\usepackage{supertabular}
\usepackage{xcolor}
\usepackage{tikz}
\usepackage{longtable}
\usepackage{tabulary}
\usepackage{colortbl}
```
To insert a table using the `supertabular` package, you create the table as shown in the following example:

```latex
\begin{flushleft}
\tablehead{}
\begin{supertabular}{|m{2cm}|m{6cm}|}
\hline
Heading 1 & Heading 2\\\hline
1st column and 1st row & 2nd column and 1st Row\\\hline
1st column and 2nd row & 2nd column and 2nd Row\\\hline
1st column and 3rd row & 2nd column and 3rd Row\\\hline
1st column and 4th row & 2nd column and 4th Row\\\hline
\end{supertabular}
\end{flushleft}
```

The environment command `\begin{flushleft}`places the table left aligned to the margin. The command `\tablehead{}` adds a table heading. In this case, it is empty so no table heading is used.

## Adding Spacing to Table Cells

You can add spacing above and below the text in table row. Use the following:

```latex
\setlength{\extrarowheight}{4pt}
```
Here is an example of it used in a table.

```latex
\begin{footnotesize}
\setlength{\extrarowheight}{7.6pt}
\begin{tabular}{l|m{7cm}}
\hline
\hline
Cell contents & Cell contents  \\\hline
\hline
Cell contents & Cell contents  \\\hline
Cell contents & Cell contents  \\\hline
Cell contents & Cell contents  \\\hline
\hline
\end{tabular}
\end{footnotesize}
```
