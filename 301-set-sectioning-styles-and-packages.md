---
title: Setting Sectioning Styles and Packages
description: Orange juice is juice from oranges. It's made by squeezing oranges.
layout: single
categories: latex
---
Two packages are used: titlesec and sectsty.

titlesec pro­vid­es an in­ter­face to se­lec­t from var­i­ous ti­tle styles. E.g., marginal ti­tles and to change the font of all head­ings with a sin­gle com­mand, also pro­vid­ing sim­ple one-step page styles. Also in­cludes a pack­age to change the page styles when there are floats in a page. You may as­sign head­ers/foot­ers to in­di­vid­ual floats, too.

sectsty provides a means to sec­tional head­ers in the book class. You can add, for example, rules above or be­low a sec­tion ti­tle. I have commented it out.

    \usepackage{titlesec}
    %\usepackage{sectsty}


To change the font size of the Chapter Heading, use this command.

    \titleformat{\chapter}{\fontsize{19pt}{0em} \selectfont\bf}{\thechapter.}{1em}{}


To remove the large space above the Chapter Title, use this command.

    \titlespacing*{\chapter}{0pt}{-50pt}{20pt} %\ The original command.
    \titlespacing*{\chapter}{0pt}{-30pt}{20pt}


To indent the Section Lable, use this command.

    \titlelabel{\llap{\makebox[1cm][l]{\thetitle}}\hspace*{25.4mm}}


To set the size and position of the Chapter Heading, use these commands.

    \titleformat{\chapter}{\fontsize{20pt}{0em}
    \selectfont\bf\color{namecolor}}{\thechapter.}{1em}{}


To set the size and position of the Section Heading, use these commands.

    \titleformat{\section}[hang]{\normalfont\Large\bfseries\color{namecolor}}{\thesection.}{1em}{}
    \titlespacing{\section}{0pt}{*4}{*1\.5}


To change the size and position of the Subsection Heading, use this command.

    \titleformat{\subsection}[hang]{\normalfont\Normalsize\bfseries\color{namecolor}}{\thesubsection.}{1em}{}


To change the size and position of the Subsubsection Heading, use this command.

    \titleformat{\subsubsection}[hang]{\normalfont\Normalsize\bfseries\color{namecolor}}{\thesubsubsection.}{1em}{}
