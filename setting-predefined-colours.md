# Defining and Using Colours

By setting colour definitions in the stylesheet, you can reference them throughout the stylesheet or in the document.

If you have corporate colours, you will need to use these colours in your documentation, perhaps on the title page or in the headers or footers.

It is best to define these colours in the stylesheet. Several commands are provided for this.

## color Package

First, you need to add colour packages. The basic colour package is added using the following command.

```latex
\usepackage{color}
```

## xcolor Package

With the `xcolor` package you can define custom colours using one of the colour models such as gray, rgb, cmyk, and so on.

```latex
\usepackage[usenames,dvipsnames,svgnames,table]{xcolor}
```

`usenames` is one of the 16 predefined colours in LaTeX. These are:

```latex
     black, blue, brown, cyan, darkgray,
     gray, green, lightgray, lime, magenta,
     olive, orange, pink, purple, red,
     teal, violet, white, yellow.
 ```

 `dvipsnames` loads a set of predefined colours.

 `svgnames` loads a set of predefined colours based on SVG definitions.

 `table` loads a predefined set of colours for use in table rows, columns and cells.

I used the `xcolour` package as I wanted to define colours based on corporate branding.

## Defining Custom Colours

To provide for a set of predefined colours that can be used throughout the document, use the `/definecolor` command with the colour type and settings as arguments. This requires that you use the `xcolor` package discussed above.

The simplest means of defining a colour is using the following:

```latex
\definecolor{name}{colour model}{specification}
```

Here are some examples using rgb and cmyk colour models:

```latex
\definecolor{red}{rgb}{1,0,0}
\definecolor[named]{Black}{cmyk}{0,0,0,1}
```

The xcolor package provides many more options. I found that I only needed to use the rgb model, give the new colour a name and define its rgb values.

## Defining Colours for Boilerplate Elements

Here are five colours that I defined within the stylesheet for using on the title page, headers and footers, and other elements. They use the rgb colour model:

```latex
% Blue for title page and other elements
\definecolor{blue}{rgb}{0,38,75}
% Orange for headers, footers and headings
\definecolor{orange}{rgb}{241,133,0}
% Gray for use as required.
\definecolor{gray}{rgb}{0.4, 0.0, 0.4}
% background color for code boxes
\definecolor{codeBackground}{RGB}{251, 251, 244}
% White for use as required.
\definecolor{codeBackground}{white}
```

## Defining Colours for Information Boxes

You can define background colour settings and line colour settings for information boxes used in the document. For example:

```latex
% Background colour for Warning Box:
\definecolor{warning}{RGB}{255,231,231}
% Background colour for Note Box:
\definecolor{note}{RGB}{255,255,211}
% Background colour for Information Box:
\definecolor{info}{RGB}{224,239,255}
% Line Color for Information Box:
\definecolor{infoline}{RGB}{158,182,212}
% Line Color for Note Box:
\definecolor{noteline}{RGB}{247,223,146}
% Two Line Colors for Warning Boxes:
\definecolor{warnline}{RGB}{51,51,51}
\definecolor{warnline}{RGB}{155,231,231}
```

## Using Colour Definitions

Once you have defined a colour, you can using it within other styles or commands in the stylesheet.

For example, I defined an orange colour as followS for the title page:

```latex
\definecolor{namecolor}{RGB}{232,134,12}
```

It has a rather odd name called `namecolor`. I then referenced this colour in the style for chapter titles.

```latex
\titleformat{\chapter}{\fontsize{20pt}{0em}\selectfont\bf\color{namecolor}}{\thechapter.}{1em}{}
```

If I want to change the colour of chapter titles, I need only change the definition of `namecolor`.

I will discuss the heading definitions in a later topic.
