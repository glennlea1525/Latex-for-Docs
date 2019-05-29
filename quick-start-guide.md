# Quick Start Guide - Overview

Summary: Quick overview to get you up and running in no time at all.

LaTeX can be used to develop very good technical documentation, but it requires the use of specific document classes, packages and settings. What follows in this and upcoming topics is entirely my own experience having to create high quality user guides and manuals using LaTeX. Much of it was trial and error until I finally landed on a good set of tools to do the job. Consultants, clients and Stack Overflow helped considerably.

So, to get you up and running quickly, I have listed the steps you need to follow to generate a pdf file from a sample LaTeX file.

**ProTip:** If you have some experience with LaTeX you can skip this topic and jump right in using the more details topics that follow this topic.

## 1. Install the Distributions and Editors

You need a properly installed TeX distribution such as ProTeXt and MacTeX. You will also need an editor such as TeXnicCenter, TeXworks or Eclipse.

**See Also:** For information about TeX distributions and LaTeX editors, see [
Selecting a LaTeX Distribution and a LaTeX Editor](http://localhost:4000/latex/04-installing_distributions/)

## 2. Create a Sample Document

Open a LaTeX editor such as TeXworks and enter in the following exactly as shown:

```latex
\documentclass[12pt]{article}
\usepackage{palatino,url}
\begin{document}
\section*{My first document}
This is a short example of a \LaTeX\ document written
\today. It shows a few simple features of automated
typesetting, including
\begin{itemize}
\item setting the default font size to 12pt
\item specifying an article type for formatting
\item using the Palatino typeface
\item adding special formatting for URIs
\item formatting a heading in section style
\item using the \LaTeX\ logo
\item generating today's date
\item formatting a list of items
\item centering and italicizing
\item autonumbering the pages
\end{itemize}
\subsection*{More information}
This example was taken from Formatting Information,
which you can download from
\url{http://www.ctan.org/tex-archive/info/beginlatex/}
and use as a teach-yourself guide.
\begin{center}
\textit{Some text to close the document}
\end{center}
\end{document}
```
Your LaTeX file should look as follows:

![Source LaTex file]
(https://github.com/glennlea1525/Latex-for-Docs/imgages/quickstart-source.jpg)

*Quick Start LaTeX file in TexWorks.*

## 3. Build (Compile) the LaTeX File to Generate a PDF Document

After entering the text, save it as `QuickStart.tex`.

The file needs to be built (or compiled) to generate a PDF file.

The preferred way is to use a LaTeX editor such as TeXworks or TeXnicCenter. You could also use the command line if you have MikTex in your path.

In TeXworks, select the build option *pdfLaTeX* from the *Build* menu, then click *Build* (the arrow next to the dropdown menu).

You should see the following results as a PDF file in a viewer.

![LaTex file output]
(https://github.com/glennlea1525/Latex-for-Docs/imgages/quickstart-output.jpg)

To build the LaTeX file using the command line:

1. Change to the directory containing `QuickStart.tex`.
1. Enter `pdflatex QuickStart.tex`.
