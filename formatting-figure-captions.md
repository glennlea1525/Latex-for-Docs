# Formatting figure captions



    \usepackage[font=small,format=plain,labelfont=bf,up,textfont=it,up]{caption}


Packages for Source Code

    \usepackage{listings}
    \usepackage{boxhandler}
    \usepackage{verbatimbox}


lstset settings &#8211; This Macro has been implemented

    \definecolor{dkgreen}{rgb}{0,0.6,0}
    \definecolor{gray}{rgb}{0.5,0.5,0.5}
    \definecolor{mauve}{rgb}{0.58,0,0.82}
    \definecolor{lightgrey}{RGB}{211,211,211}

    \lstset{frame=tlrb, frameround=tttt, framerule=0.2pt, rulecolor=\color{lightgrey}, language=SQL,
     aboveskip=3mm, belowskip=3mm, showstringspaces=false, columns=flexible, basicstyle={\small\ttfamily},
     numbers=none, numberstyle=\tiny\color{gray}, keywordstyle=\color{blue}, commentstyle=\color{dkgreen},
     stringstyle=\color{mauve}, breaklines=true, breakatwhitespace=true tabsize=3 }

    \lstset{language=SQL}

    \newcommand{\inlineCode}{\lstinline[basicstyle=\normalsize\ttfamily]}


Use this Macro in the Latex document as follows:

    %\begin{lstlisting} % INSERT CODE HERE %\end{lstlisting} %
