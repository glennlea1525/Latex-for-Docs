---
title: Quick Start Guide
description: Quick overview to get you up and running in no time at all.
layout: single
categories: latex
---
LaTeX can be used to develop very good technical documentation, but it requires the use of specific document classes, packages and settings. What follows in this and upcoming topics is entirely my own experience having to create high quality user guides and manuals using LaTeX. Much of it was trial and error until I finally landed on a good set of tools to do the job. Consultants, clients and Stack Overflow helped considerably.

So, to get you up and running quickly, I have listed the steps you need to follow to generate a pdf file from a sample LaTeX file.

**ProTip:** If you have some experience with LaTeX you can skip this topic and jump right in using the more details topics that follow this topic.
{: .notice--info}

## 1. Install the Distributions and Editors

You need a properly installed TeX distribution such as ProTeXt and MacTeX. You will also need an editor such as TeXnicCenter, TeXworks or Eclipse.

**See Also:** For information about TeX distributions and LaTeX editors, see [
Selecting a LaTeX Distribution and a LaTeX Editor][dist hp].
{: .notice--info}

[dist hp]: http://localhost:4000/latex/04-installing_distributions/ "hp"

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

<img src="/assets/images/latex/quickstart-source.jpg" alt="Quick Start Guide Output" style="width:441px;height:506px;">
<figcaption>Quick Start LaTeX file in TexWorks.</figcaption>


## 3. Build (Compile) the LaTeX File to Generate a PDF Document

After entering the text, save it as `QuickStart.tex`.

The file needs to be built (or compiled) to generate a PDF file.

The preferred way is to use a LaTeX editor such as TeXworks or TeXnicCenter. You could also use the commmand line if you have MikTex in your path.

In TeXworks, select the build option *pdfLaTeX* from the *Build* menu, then click *Build* (the arrow next to the dropdown menu).

You should see the following results as a PDF file in a viewer.

<img src="/assets/images/latex/quickstart-output.jpg" alt="Quick Start Guide Output" style="width:550px;height:700px;">
<figcaption>Quick Start LaTeX file output.</figcaption>

To build the LaTeX file using the command line, change to the directory containing `QuickStart.tex`, then enter `pdflatex QuickStart.tex`.
