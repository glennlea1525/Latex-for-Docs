---
title: Setting Style Definitions for Note, Info, and Warning Boxes
description: Orange juice is juice from oranges. It's made by squeezing oranges.
layout: single
categories: latex
---
**Definition for Warning Boxes**

This long bit of LaTeX defines the rules, spacing, icon and background colour of a warning box. A Warning Box is information that you must be aware of before you perform a specific task. You can copy and adjust these settings as needed.

    \newmdenv[ roundcorner=10pt, skipabove=10pt skipbelow=10pt leftmargin=20pt, rightmargin=20pt, backgroundcolor=warning,
      innertopmargin=30pt, innerbottommargin=10pt, innerleftmargin=70pt, middlelinewidth=0pt, everyline=true, linecolor=warnline,
      font=\normalfont\normalsize, shadow=false, frametitlefont=\normalfont\normalsize\bfseries, frametitleaboveskip=1em,
      singleextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O) {\includegraphics[scale=0.40]
      {sharedimages/alerticon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,font=\bfseries,xshift=10pt]
      at (P-|O) {Warning};}, firstextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O)
      {\includegraphics[scale=0.40]{sharedimages/alerticon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,
      font=\bfseries,xshift=10pt] at (P-|O) {Warning};} ]{warnbox}


Then, to insert a warning box into the document flow, use the following commands.

    \begin{warnbox}
    \lipsum[4]
    \end{warnbox}    


**Definition for Note Boxes**

This long bit of LaTeX is essentially the same as defined for the Warning Box, with the exception of the background colour and the icon used in the box. Note Boxes are additional information that is important but outside the procedure described in the current text flow.

    \newmdenv[ roundcorner=10pt, skipabove=10pt skipbelow=10pt leftmargin=20pt, rightmargin=20pt, backgroundcolor=note,
      innertopmargin=30pt, innerbottommargin=10pt, innerleftmargin=70pt, middlelinewidth=0pt, everyline=true, linecolor=warnline,
      font=\normalfont\normalsize, shadow=false, frametitlefont=\normalfont\normalsize\bfseries, frametitleaboveskip=1em,
      singleextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O) {\includegraphics[scale=0.40]
      {sharedimages/tipsicon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,font=\bfseries,xshift=10pt]
      at (P-|O) {Note};}, firstextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O)
      {\includegraphics[scale=0.40]{sharedimages/tipsicon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,
      font=\bfseries,xshift=10pt] at (P-|O) {Note};}]{notice}  


Then, use the following commands to insert a Note Box into the document flow.

    \begin{notice}
    \lipsum[4]
    \end{notice}


**Definition for Info Boxes**

Like the Warning and Note Box definitions above, you can adjust the settings as required. An Info Box would normally be used to provide additional information that may be available outside the current document, such as a website or another user manual.

    \newmdenv[ roundcorner=10pt, skipabove=10pt skipbelow=10pt leftmargin=20pt, rightmargin=20pt, backgroundcolor=info,
      innertopmargin=30pt, innerbottommargin=10pt, innerleftmargin=70pt, middlelinewidth=0pt, everyline=true, linecolor=warnline,
      font=\normalfont\normalsize, shadow=false, frametitlefont=\normalfont\normalsize\bfseries, frametitleaboveskip=1em,
      singleextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O) {\includegraphics[scale=0.40]
      {sharedimages/noticeicon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,font=\bfseries,xshift=10pt]
      at (P-|O) {Information};}, firstextra={ \node[inner sep=0pt,anchor=north west,xshift=10pt,yshift=-30pt] at (P-|O)
      {\includegraphics[scale=0.40]{sharedimages/noticeicon}}; \node[inner sep=0pt,anchor=north west,yshift=-.8\baselineskip,
      font=\bfseries,xshift=10pt] at (P-|O) {Information};} ]{infobox}


Then, use the following commands to insert an Info Box into the document flow.

    \begin{infobox}
    \lipsum[4]
    \end{infobox}
