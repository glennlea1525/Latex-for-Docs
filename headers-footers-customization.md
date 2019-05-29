# Creating Custom Headers and Footers

Using the fancyhdr package, you can create customized headers and footers.

Page headers and footers in LaTeX are defined by the `\pagestyle` and `\pagenumbering` commands.

`\pagestyle` defines the general contents of the headers and footers, such as where the page numbers will be printed.

`\pagenumbering` defines the format of the page number.  

To make the headers and footers more informative, I used the `fancyhdr` package.

I used this command because I wanted more than just the standard header provided by default. I wanted to have different headers and footers for odd and even pages, different headers and footers for chapter pages and control over font sizes, and so on.

**See Also:** Information about the _fancyhdr_ class is available <a href="http://www.ctex.org/documents/packages/layout/fancyhdr.pdf">here</a>.
{: .notice--info}

## Defining a Header and Footer with fancyhdr

You define the header and footer in the stylesheet. In this case, the package `fancyhdr` is used with the page style `fancy`.  

### Use the package `fancyhr`
The following shows the relevant section in the stylesheet that defines the headers and footers of the document.

```latex
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhf{}
```
### Define the Font Used in the Header/Footer

The font defined is 9 pt Helvetica which is defined using the short form `phv`. The text of the headers and footers use the `titlepagecolor` for the background,

```latex
\newcommand{\helv}{\fontfamily{phv}
\color{titlepagecolor}
\fontseries{b}
\fontshape{n}
\fontsize{9}{11}\selectfont}
```

This can be a single line as follows:

```latex
\newcommand{\helv}{\fontfamily{phv}\color{titlepagecolor} \fontseries{b} \fontshape{n}\fontsize{9}{11}\selectfont}
```

The `titlepagecolor` which has been defined elsewhere in the stylesheet as:

```latex
\definecolor{titlepagecolor}{RGB}{0,38,75}
```

### Grab the Chapter and Section Text

The text of the chapter is pulled in using `\chaptermark` while the macro `\thechapter` pulls in the chapter number. Similarly, the text of the section heading is pulled in using `\sectionmark` while the macro `thesection` pulls in the number of the section.

```latex
\renewcommand{\chaptermark} [1] {\markboth{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark} [1] {\markright{\helv\NoUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\helv\thesection.\ #1}}
\renewcommand{\chaptermark}[1]{\markboth{\helv\thechapter.\ #1}{}}
```

### Eliminate the Decorative Line

No decorative line is used to separate the header from the body text so it is eliminated using:

```latex
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{0pt}
```

### Define the Footer Text

The footer, in this example, inserts a page number and copyright.

```latex
\fancyfoot[LE,RO]{\helv Page \thepage}
\fancyfoot[RE,LO]{\helv Copyright \copyright 2017 Glenn J. Lea. Confidential}
```











    \renewcommand{\headrulewidth}{0pt}
    \renewcommand{\footrulewidth}{0pt}

## Inserting fancyhead Into the Root File

After defining the headers and footers in the stylesheet, you insert the header into the root file after the `\frontmatter` environment command.

    \begin{document}
    \frontmatter
     % Configuration of the header strings for the frontmatter pages.
    \setcounter{tocdepth}{3}
    \fancyhead[RE,LO]{}

It is important where you place this command. The LaTeX typesetter my know how to build the headers and footers before any geometry is defined. After calling the \fancyhead command, you can go ahead and input your files, and so forth.

## Inserting Copyright Information

Insert copyright information here

    \fancyfoot[RE,LO]{\helv Copyright \copyright 2016 Glenn J. Lea}


Alternate copyright footer information

    %\lfoot{\thepage} %\cfoot{Copyright \copyright 2016 Glenn J. Lea}
    %\rfoot{Document ID}

## Header and Footer Example

The following shows the resulting pages with headers and footers.

<img src="/assets/images/latex/header-footer-pg01.jpg" alt="Sample Chapter Page" style="width:556px;height:771px;">
<figcaption>Sample Chatper page showing footer</figcaption>

<img src="/assets/images/latex/header-footer-pg02.jpg" alt="Sample Even Page" style="width:557px;height:781px;">
<figcaption>Sample Chatper page showing footer</figcaption>   
