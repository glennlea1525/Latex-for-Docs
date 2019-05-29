# Creating a Custom Title Page

LaTeX has the capability of defining quite good looking title pages. Not easy, but doable.

LaTeX comes with a standard title page, but you can create your own custom title page.

You can start your own development of a title page by using this sample LaTeX title page file.

## Title Page Properties

The settings here define the background colour of the title page and the colour of any text used on the title page. In this case, the entire background is a dark blue while the text is an orange colour. It makes for a striking colour for the title page, but a white colour would be just as good, if not better. However, whatever is set here is generally a branding colour so we only provide a suggested set of properties.

The xcolor and graphicx packages are used here.

```latex
\usepackage{xcolor}
\definecolor{titlepagecolor}{RGB}{0,38,75} % Blue
\definecolor{namecolor}{RGB}{241,133,0} % Orange
```

## Input Title Page in Root File

You create a title page in its own file subdirectory of the project directory. In my case, I created a file called something descriptive such as `titlepage.tex`and saved it in the subdirectory where I kept all the chapter files.

    Root file
    ├── \usepackage{styles/stylesheet}         # Insert Stylesheet
    ├── \documentclass[properties]{book}       # Use Book class
    ├── \begin{document}                       # Required element
    ├── \frontmatter                           # Frontmatter of the Document
    ├── \setcounter{tocdepth}{3}               # Number of heading in TOC
    ├── \fancyhead[RE,LO]{}                    # Header package
    ├── \input{subdir/titlepage.tex}           # Input Title page (separate doc)
    ├── \newpage                               # Insert page break
    ├── \pagecolor{white}

The title page uses the `\input` command. This just dumps the importing the commands and text directly into the typesetting stream at precisely the point where the input command is placed in the root file. The `\input` and `\include` commands are discussed in more detail in an later topic.

Before you include the command `\input{subdir/titlepage.tex}` the typesetter needs to know the depth of the Table of Contents using the command `\setcounter{tocdepth}{3}` (it has been set to 3 levels).

Next, you include the command for the headers and footers `\fancyhead[RE,LO]{}`.
The `\fancyhead` command is defined within the stylesheet. Headers and footers will be discussed in a later topic.

## Sample Title Page

Here is a sample title page that you use to begin defining your own title page. Play around with the commands, google for other ideas and come up with your own title page.

```latex
%***********************************************************************
% Title Page for Sample Manual
% Copyright Year Glenn J. Lea
%***********************************************************************
\typeout{**** Titlepage}
\typeout{****}
\typeout{**** titlepage.tex}

{
\begin{titlepage}
\addcontentsline{toc}{chapter}{Sample Manual}
% defines the geometry for the titlepage
\newgeometry{left=5cm,top=6cm}
\pagecolor{titlepagecolor}
\noindent
%\includegraphics[width=10.91cm, height=2.33cm]{images/logo.png}\\[-1em]
\color{white}
\makebox[0pt][l]{\rule{1.3\textwidth}{1pt}}
\par
\noindent
%\textbf{\textsf{Company name}}
\textcolor{namecolor}{\large\textsf{Sample Subtitle}}
\vfill

{\huge \textsf{Document Name}}
\vskip\baselineskip
\noindent

\textcolor{namecolor}{\large\textsf{Date}}\\[0.25cm]
\textcolor{namecolor}{\large\textsf{Copyright \copyright \ Company}}

\restoregeometry % restores the geometry
\end{titlepage}
}

\clearpage
\pagecolor{white} % Use this to restore the color pages to white
```

## Title Page Details

Start, of course, with document information.

```latex
%***********************************************************************
% Title Page for Sample Manual
% Copyright Year Glenn J. Lea
%***********************************************************************
```

Optionally, you can add a command to typeout to terminal the currently processed file.

```latex
\typeout{**** Titlepage}
\typeout{****}
\typeout{**** titlepage.tex}
```

Then, include an opening environment command.

```latex
\begin{titlepage}
```
Add the cover to the TOC so it becomes the top link in a TOC, the Home link, as it were.

```latex
\addcontentsline{toc}{chapter}{Sample Manual}
```

Next define the page margins. The following command puts a left/right margin at 5cm and a top/bottom margin at 6cm.

```latex
\newgeometry{left=5cm,top=6cm}
```

I wanted a page colour of dark blue as the entire background of the title page. Within the stylesheet I defined a `titlepagecolor` and then used this color as an argument for the `\pagecolor` command.

```latex
\pagecolor{titlepagecolor}
```

Remove any indentation so the next elements use the margin as reference points.

```latex
\noindent
```

I want to place the company logo at a specified location using the `\includegraphics` command and setting the precise location using options. I used a png file type for the logo, but a tiff or some other high resolution file would be acceptable if the document will be printed.

```latex
\includegraphics[width=10.91cm, height=2.33cm]{images/logo.png}\[-1em]
```

Incidentally, I placed all images within a single directory called `images` which makes referencing graphics convenient.

Now, I need a background color.

```latex
\color{white}
```

Then I create a frame box with the set specifications.

```latex
\makebox[0pt][l]{\rule{1.3\textwidth}{1pt}}
```

Inside this box, I need a new paragraph.

```latex
\par
```

Now, I need to remove any indentation so that the paragraph starts at the left-hand side of the frame box.

```latex
\noindent
```

Then, add the element for product name

```latex
%\textbf{\textsf{COMPANY NAME}} % Commented out, unless required.
\textcolor{namecolor}{\large\textsf{PRODUCT NAME}}
\vfill
```

A spacing is inserted between the top text and the document title using the `\vfill` command.

Next, the document title is inserted.

```latex

{\huge \textsf{DOCUMENT TITLE}}
\vskip\baselineskip
\noindent

\textcolor{namecolor}{\large\textsf{DATE}}[0.25cm]
\textcolor{namecolor}{\large\textsf{Copyright \copyright \ COMPANY NAME}}
```

Finally, restore the geometry and close off the title page so the typesetter can continue with the next command in the root file.

```latex
\restoregeometry
\end{titlepage}
}
```

This restores the color pages to white, or to no colour.

```latex
\clearpage
\pagecolor{white}
```
The following shows the resulting title page.

<img src="/assets/images/latex/titlepage.png" alt="Sample Title Page" style="width:533px;height:751px;">
<figcaption>Sample Title Page</figcaption>
