---
title: Customizing Lists and Indentation
description: Orange juice is juice from oranges. It's made by squeezing oranges.
layout: single
categories: latex
---
Package for resuming enumeration after intervening text element.

    \usepackage{enumitem}


Command to indent paragraphs within lists

\newenvironment{myindentpar}\[1\]\[1\]% {\begin{list}{}% {\setlength{\leftmargin}{#1}}% \item[]% } {\end{list}}

And use myindentpar in the text as follows

    \begin{myindentpar}{1cm} % text text text... % \end{myindentpar}


Note that the indent can be adjusted as required in the text.


\documentclass{article} \usepackage{enumitem} \begin{document}

\begin{enumerate} \item List item \item Another list item \end{enumerate}

Paragraph of comments on list items 1 and 2.

\begin{enumerate}[resume] \item Further item \item Final item \end{enumerate}

\end{document}

How to Interrupt/resume an enumerated list:

http://stackoverflow.com/questions/1348194/how-to-interrupt-resume-a-list-in-latex
