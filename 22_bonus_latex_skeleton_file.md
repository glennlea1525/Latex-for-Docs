I found this LaTeX skeleton on the TEX StackExchange Site by a user named XPort. I thought it was quite cool and useful. So I reproduced it here:

Step 1 - Create Project Directories

Divide your project into at least 3 sub directories:

*   MyProject\Contents
*   MyProject\Images
*   MyProject\Codes.

Step 2 - Create a Document Class mybook.cls

Create your own document class, namely mybook.cls as follows and save it in MyProject directory.

\ProvidesClass{mybook}[2011/06/07 v 0.01 my own class (hv)] \DeclareOption*{\PassOptionsToClass{\CurrentOption}{book}} \ProcessOptions\relax \LoadClass [ %other default options go here ]{book}

\newcommand\ContentsPath{Contents/} \newcommand\ChapterPath{\ContentsPath} \newcommand\SectionPath{\ChapterPath} \newcommand\SubSectionPath{\SectionPath}

\@ifclassloaded{book} { \newcommand\IncludeChapter[1] { \renewcommand\ChapterPath{\ContentsPath#1/} \include{\ContentsPath#1} } \newcommand\IncludeOnlyChapter[1] { \includeonly{\ContentsPath#1} } }{}

\newcommand\InputSection[1] { \renewcommand\SectionPath{\ChapterPath#1/} \input{\ChapterPath#1} }

\newcommand\InputSubSection[1] { \renewcommand\SubSectionPath{\SectionPath#1/} \input{\SectionPath#1} }

\newcommand\InputSubSubSection[1] { \input{\SubSectionPath#1} }

\@ifclassloaded{book} { \newcommand\Chapter[1] { \chapter{#1} %\addcontentsline{toc}{chapter}{#1} } }{}

\newcommand\Section[1] { \section{#1}% %\addcontentsline{toc}{section}{#1} }

\newcommand\SubSection[1] { \subsection{#1} %\addcontentsline{toc}{subsection}{#1} }

\newcommand\SubSubSection[1] { \subsubsection{#1} %\addcontentsline{toc}{subsubsection}{#1} }

\RequirePackage{xcolor}

\RequirePackage{listings} \lstdefinestyle{Common} { breaklines=true, tabsize=3, showstringspaces=false, aboveskip=0pt, belowskip=0pt, extendedchars=\true, language=PHP, frame=single,  
%=========================================================== framesep=3pt,%expand outward. framerule=0.4pt,%expand outward. xleftmargin=3.4pt,%make the frame fits in the text area. xrightmargin=3.4pt,%make the frame fits in the text area. %=========================================================== rulecolor=\color{Red}% }

\lstdefinestyle{ThemeA} { style=Common, backgroundcolor=\color{Yellow!10}, basicstyle=\scriptsize\color{Black}\ttfamily, keywordstyle=\color{Orange}, identifierstyle=\color{Cyan}, stringstyle=\color{Red}, commentstyle=\color{Green} }

\newcommand{\IncludeCode}[2][style=ThemeA] { \lstinputlisting[#1,caption={\href{#2}{#2}}]{#2} }

\RequirePackage[colorlinks=true,bookmarksnumbered=true,bookmarksopen=true]{hyperref} \RequirePackage[all]{hypcap}

\RequirePackage{makeidx} \makeindex

\endinput

Step 3 - Create main.tex (Main Input File)

Create the main input file, namely main.tex as follows and save it in MyProject.

\documentclass[dvipsnames,cmyk,12pt]{mybook} \usepackage[a4paper,vmargin=15mm,hmargin=10mm]{geometry}

\title{Introduction to PHP} \author{Your Name} \date{\today}

%\IncludeOnlyChapter{Variables}

\begin{document} \frontmatter \maketitle \thispagestyle{empty} \tableofcontents \lstlistoflistings \mainmatter \part{Part 1} \IncludeChapter{Variables} \IncludeChapter{Array} \part{Part 2}  
\IncludeChapter{Interface} \IncludeChapter{SubClass} \appendix\renewcommand{\chaptername}{\appendixname} \part{Appendix} \IncludeChapter{YourAppendix} \backmatter \printindex \end{document}

Step 4 - Create Variables.tex (Chapter variables file)

Create a file for chapter Variables, namely Variables.tex, as follows and save it in MyProject\Contents.

\Chapter{Variables} \InputSection{Declaration} \InputSection{Instantiation}

Step 5 - Create Variables Directory

Create a directory MyProject\Contents\Variables.

Step 6 - Create Declaration.tex (Section Declaratios)

Create a file for section Declaration, namely Declaration.tex, as follows and save it in MyProject\Contents\Variables.

\Section{Declaration}

\IncludeCode[style=ThemeA]{Codes/Declaration.php}

Step 7 - Repeat for Remaining Content

Do the same for the remaining contents.

Notes

It is also worth using VCS (versioning control system) such as Subversion or Git to manage your project.
