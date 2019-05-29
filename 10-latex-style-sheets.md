---
title: About LaTex Stylesheets
description: Use a stylesheet to easily maintain all the styles used by the document.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

Style Sheets are a useful method of organizing all the styles that are used in your LaTeX document into a single file.

## Why Use Style Sheets?

You could put all your styles in the head of each `.tex` file in your project but that makes no sense, especially if you have multiple files referring to the same style sheet.

Furthermore, keeping all your styles in a single file makes maintaining the styles vastly easier. You could comment out particular commands, especially commands that include chapters, to help you during your development process.

You could also comment out chapters that are specific to outputs. I am sure there are other ways of doing this, but for me, simplicity is key, so commenting out of a command or include works.  

Another useful way you could use stylesheets is to include examples of how to use a particular style (commented out, of course).

## Using a Stylesheet Subdirectory

In my projects, I have created a subdirectory called `\styles`, not surprisingly, and I have placed in this directory a single style sheet called `mystyles`. If you need more than one stylesheet, you could place them in this subdirectory. You could also have several stylesheets for specific outputs, etc. and just comment out the unneeded stylesheet in the root file.  

    Project Root
    ├── manual-ROOT.tex        # document root file
    ├── \styles                # stylesheet subdirectory
    ├── \chapters              # subdirectory to store all chapters
    ├── \append                # subdirectory to store any appendices
    ├── \images                # subdirectory for shared images

## Including the Stylesheet in the Root File

You include a command to use the stylesheet immediately following the `\documentclass` command but before the `\begin{document}` command.

```latex
\documentclass[properties]{book} # Use Book class
\usepackage{styles/stylesheet}   # Insert Stylesheet
\begin{document}                 # Required element
```

## Prologue: Copyright and Author Information

You should begin the stylesheet with copyright information. The reasons should be obvious.

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%
% Document User Guide Styles Template
% Author: Glenn J. Lea Technical Writer
% Website: www.glennjlea.ca
% Date: Month Year
% Copyright 2017 Glenn J. Lea
%
% %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
```

## Organizing a Stylesheet

I kept all related styles together within sections in the stylesheet. I divided the sections using comments so I could easily find a style, should it need changing, deleting, etc.

The sections I used were as follows:

```latex
% Document Class Information
\commmands

% Packages
\commmands

% Default packages
\commmands

% Custom Columns for formatting tabular material
\commmands

% PDF metadata settings
\commmands

% Adding ToDo notes in document
\commmands

% Language selection
\commmands

% Graphics support
\commmands

% Font selection styles and packages
\commmands

% Title page commands
\commmands

% Color definitions
\commmands

% Warning, Notes, Info box color schemes
\commmands

% Sectioning styles and packages
\commmands

% URL styles and packages
\commmands

% Page size, margins and layout
\commmands

% Line spacing and settings
\commmands

% Header and footer settings and customization
\commmands

% Figure captions
\commmands

% Source code environments
\commmands

% Customized lists and indentation
\commmands

% Table-related styles
\commmands

% Warning, notes, info box style definitions
\commmands

% Experimental commands
\commmands
```

As you can see, the main work to create high-quality technical documentation is in the stylesheet. This took a considerable amount of time to develop. Getting it right is critical for the quality of the documentation.

The upcoming topics will refer to the stylesheet frequently. You define the style then you need to implement it in the document. Hence, discussing a topic requires discussing both the stylesheet and its implementation.
