# Some Experimental Stuff

## Footnote rules

This sets the footnote rule which would appear just above the first footnote on a page, if used:

    \setlength{\skip\footins}{0.119cm}
    \renewcommand\footnoterule{\vspace*{-0.018cm}
    \setlength\leftskip{0pt}
    \setlength\rightskip{0pt plus 1fil}
    \noindent\textcolor{black}{\rule{0.25\columnwidth}{0.018cm}}\vspace*{0.101cm}}


## Widow and Orphan Control

You can control widows and orphans using these commands:

    \widowpenalty=300
    \clubpenalty=300


## Adding To Do notes

You can add this Package to add todo notes in the document as a type of comment:

    \usepackage{todonotes}

Then insert a note in the doc using the following:

    \todo{Rewrite this answer \ldots}

At any location in the document a list of the inserted notes can be generated with the following command:

    \listoftodos
