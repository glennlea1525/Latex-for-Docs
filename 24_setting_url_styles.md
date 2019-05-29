To nicely format and linebreak URLs, use this command.

    \usepackage{url}


To define a new 'leo' style for the package that will use a smaller font, use these commands.

    \makeatletter
    \def\url@leostyle{% \@ifundefined{selectfont}{\def\UrlFont{\sf}}{\def\UrlFont{\small\ttfamily}}}
    \makeatother


To use the newly defined style, use this command.

    \urlstyle{leo}
