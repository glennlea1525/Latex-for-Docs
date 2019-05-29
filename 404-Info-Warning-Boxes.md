% Definition for Obsolete Note Boxes                     

\mdfdefinestyle{notebox}{roundcorner=10pt,
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=note,
  innertopmargin=.5em,
  innerbottommargin=10pt,
  innerleftmargin=10pt,
  middlelinewidth=0pt,
  font=\normalfont\normalsize,
  shadow=true,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
}                      

% Definition for Obsolete Info Boxes                     
\mdfdefinestyle{infobox}{roundcorner=10pt,
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=info,
  innertopmargin=.5em,
  innerbottommargin=10pt,
  innerleftmargin=10pt,
  middlelinewidth=0pt,
  font=\normalfont\normalsize,
  shadow=true,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
}                      

% Definition for Obsolete Warning Boxes                     
\mdfdefinestyle{warn}{roundcorner=10pt,
  skipabove=10pt
  skipbelow=10pt
  leftmargin=20pt,
  rightmargin=20pt,
  backgroundcolor=warning,
  innertopmargin=10pt,
  innerbottommargin=10pt,
  innerleftmargin=10pt,
  middlelinewidth=0pt,
  everyline=true,f
  linecolor=warnline,
  font=\normalfont\normalsize,
  shadow=true,
  frametitlefont=\normalfont\normalsize\bfseries,
  frametitleaboveskip=1em,
}                      


% Then insert this text into a document
%\begin{mdframed}[style=item,frametitle=title]
%This is the text.
%\end{mdframed}
%
% or
%
%\begin{mdframed}[style=exampledefault]
%This is some text.
%\end{mdframed}

The following is an example Info Box.

\begin{mdframed}[style=infobox, frametitle=Information]
\includegraphics[scale=0.50]{sharedimages/noticeicon} \\ This is a dummy Info.
\end{mdframed}

The following is an example Warning Box.
\begin{mdframed}[style=warn,frametitle=Warning]
\includegraphics[scale=0.50]{sharedimages/alerticon} \\ \This is a dummy warning.
\end{mdframed}

The following is an example Note Box
\begin{mdframed}[style=notebox, frametitle=Note]
\includegraphics[scale=0.50]{sharedimages/tipsicon} \\ This is a dummy Note.
\end{mdframed}
