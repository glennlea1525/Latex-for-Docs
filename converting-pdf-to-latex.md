# Converting Source PDF Files to LaTeX Files

What if you only had PDF files as your source material? How do you convert them to LaTeX?

Sometimes the only source material you have been provided to start creating the user guide are PDF files written in some other documentation tool or editor.

You could just ask for the original file but sometimes all you can have are PDF files. This was my conundrum.

The tools I used to convert the PDF file to a set of LaTeX files included the following:

* Adobe Acrobat, or some similar PDF reader that can export to Word or OpenOffice.
* OpenOffice to open the converted pdf files and save them as OO files.
* writer2latex installed in Open Office to convert the OO file to LaTeX files
* NotePad++ or a LaTeX editor to edit the resultant files

## PDF Source Material

The only source files I had were PDF files which were exported from a Confluence Content Management System. My task was to convert the pdf files to LaTeX.

Initially, I thought I could just copy out the text of the pdf file, but that quickly turned into a nightmare. So I ditched the Copy/Paste option.

Then I thought how about finding a way to export to a text file directly from PDF. Again, I'd be just left with one long text file and another massive headache. Not that option either.

I needed to find a way to generate text files of each section and subsection in the PDF file.

## Converting the PDF to LaTeX using writer2latex

After some research I found a software plugin that could generate a set of LaTeX files from Open Office. The solution I stumbled upon was to use a very helpful tool called _writer2latex_. This meant I needed to install OpenOffice (free) as well as a Java Runtime Environment (also free).

To use this tool I needed to be able to export the PDF file to a Word file or an Open Office file. Adobe Acrobat provides an `export to Word`function.

**Note:** In the following procedures, I assume you are using Windows 10 and that you have OpenOffice and a Java Runtime Environment installed. If not, please install them before continuing.
{: .notice--info}

### Downloading and Installing writer2latex

writer2latex requires a Java Runtime Environment, version 6 or later. Ensure the JRE is installed first before doing the following:  

  1. Download Writer2LaTeX <a href="https://extensions.libreoffice.org/extensions/writer2latex-1">here</a>.
  2. In the dialog that appears, click **Open** with OpenOffice.org, then click OK.
  3. In the OpenOffice Extension Manager, click **OK** to dismiss the Information dialog.
  4. After the extension has been installed, click **Close** to dismiss the dialog.

### Create the LaTeX files Using writer2latex in OpenOffice

In the following procedure, you use writer2latex to output LaTeX files.

**To create the LaTeX files**

  1. Open the PDF file in Adobe Acrobat Reader, or similar.
  2. Select *Export to Word* (or a similar menu option)
  3. Open the exported Word file in OpenOffice.
  4. From the *File* menu in OpenOffice, select *Export*.
  5. In the *Export* dialog, select **LaTeX 2e** from the **Save as type** dropdown, then click **Save**.
  6. In the **LaTeX Options** dialog, accept the default settings or make changes as required, then click **Export**.
  7. A set of LaTeX files (.tex files) will appear in the export directory.

### The Converted LaTeX File

The following is part of an example LaTeX output from the conversion process described above. Note the number of packages added by writer2latex.

```latex
% This file was converted to LaTeX by Writer2LaTeX ver. 1.0.2

% article document class used
\documentclass{article}

% Packages used by this document

\usepackage[utf8]{inputenc}
\usepackage[T3,T1]{fontenc}
\usepackage[english]{babel}
\usepackage[noenc]{tipa}
\usepackage{tipx}
\usepackage[geometry,weather,misc,clock]{ifsym}
\usepackage{pifont}
\usepackage{eurosym}
\usepackage{amsmath}
\usepackage{wasysym}
\usepackage{amssymb,amsfonts,textcomp}
\usepackage{array}
\usepackage{supertabular}
\usepackage{hhline}
\makeatletter
\newcommand\arraybslash{\let\\\@arraycr}
\makeatother
\setlength\tabcolsep{1mm}
\renewcommand\arraystretch{1.3}

\title{Your Amazing Content Title}
\author{Glenn J. Lea}
\date{2017-01-01}

\begin{document}

Document Content

\section{Section Content}

Amazingly interesting stuff you put here, isn't it?

\subsection{Subsection Content}

I just can't believe you wrote this? It is just amazing!

\begin{itemize}
\item First item in the list
\item Second item in the list
\end{itemize}

\end{document}

```

Each chapter was saved to its own LaTeX file. This root file is then used as the basis for creating the document's root file, style sheet and so on.
