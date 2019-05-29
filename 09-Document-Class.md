---
title: Selecting the Document Class
description: The documentclass command tells the LaTeX typesetter how to handle the document and which document package to use to typeset the output.
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

This is probably the most important decision you need to make for creating technical documentation using LaTeX. After looking at several types of document classes, I settled on the *book* class as the best fit to do the job. Other documentclass types did not have the capability to output long documents with proper headers and footers and all the required elements of a high quality technical document.

## The _memoir_ Class

I looked at the _memior_ class. The author of this class, Peter Wilson, describes the memoir class as best suited for "type­set­ting po­etry, fic­tion, non-fic­tion, and math­e­mat­i­cal works." It can use a wide range of font sizes, has quite a number of page styles to choose from as well as chapter styles to customize your document. It is very useful.

I tried to use this class first, but it just didn't suit my needs. I needed more flexibility in designing my title pages, adding headers and footers, and so forth. Frankly, I can't remember all the reasons why I didn't choose memoir, but in the end, it just didn't suit my needs.

**See Also:** Information about the _memoir_ class is available <a href="https://www.ctan.org/pkg/memoir?lang=en">here</a>.
{: .notice--info}

## The _book_ Class

After it seems like forever searching for that ideal class for technical documents, the solution was staring me in the face. The basic _book_ class had all the requirements I needed. It was customizable and it was designed specifically for books, that is, long documents.

**See Also:** Information about the _book_ class is available <a href="https://www.ctan.org/pkg/book?lang=en">here</a>.
{: .notice--info}

## Using the _book_ Class

You set the `\documentclass` in the document root file at the top of the file. The following documentclass command shows how I set it up:

        \documentclass[a4paper,11pt,twoside]{book}

The class is set at the end of the command within the curly brackets, while the arguments are included within the square brackets.

This command includes a number of options. It tells the LaTeX typesetter to output a document with an A4 paper size, use an 11pt font and use double-sided printing.

### Setting the Paper Size

As I was producing the document for European audiences, the paper size needed to be A4. You can choose `letter` for North American audiences.

  * `a4paper` sets the page size to 210 × 297 millimeters or 8.27 × 11.69 inches.

### Setting the Base Font Size

 A good readable base font size is 11 points. 10 points or 9 points is too small for technical documentation. These documents are used by people in a hurry or having difficulty or wanting to know how to do some task. Why strain their eyes on a very small font size.

  *  `11pt` which is quite readable for user documentation.

### Setting Pagination

I want the typesetter to paginate on two sides so I don't end up with blank pages after each page. Setting two-sided makes the document doublesided, but DOES NOT tell the printer to print double-sided. This is important for page numbering, chapter titles and section titles in headers and footers. The book class is double-sided by default.

  * `twoside` which makes the document double-sided. The margins on the left and right pages are mirrored.

## Including the Class in the Document Stylesheet

I haven't discussed stylesheets yet (it will be discussed in a later topic), but it is a good practice to include the `\documentclass` command in the first section of your style sheet.

These commands are actually implemented in the `main.tex` file but you include it in the stylesheet (and commented out) so you can see at a glace the type of document this style sheet will generate.

For example:

```latex
% Document Class Information
%
% Template: book
% Paper Size: A4
% Base point size: 11 pt
%
%\RequirePackage[l2tabu, orthodox]{nag}  
    % Uncomment the nag command to show errors in output
%\documentclass[a4paper,11pt,twoside]{book}
```

**ProTip:** Note the additional `nag` package. This package will warn you if you use wrong LaTeX in your document. I can be useful and helpful. In my case, I commented it out but made it available in the style sheet should I need to use it after making any major changes to the document.
{: .notice--info}
