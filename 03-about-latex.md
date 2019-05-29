---
title: A Very Brief Introduction to LaTeX
description: As the title says!
layout: single
categories: latex
---
{% include toc icon="gears" title="Contents" %}

## My Unexpected Deep Dive into LaTeX

A client requested that I use LaTeX to produce their set of documentation. After taking a deep breath and saying OK, I went about trying to figure out how to do this.

At the time I had zero experience with this system. LaTeX is, after all, typically used to write academic and scientific writing and is not often used for high quality product technical documentation.

And frankly, it doesn't come "out of the box" very well prepared for doing that. In fact, there is "no box" for it to come out of. LaTeX separates content from layout so you need to know the commands/markup language of LaTeX. You also need to know how to generate output.

## Its Lah-tech

As it turned out, with a little work (actually a lot of work) LaTeX can produce quite reasonable technical documentation. However, it only is capable of outputting to PDF. I could be wrong on this, so if you know of a way of outputting to HTML, I'd love to hear about it.

Incidentally, LaTeX is pronounced as "Lah-tech". Why? No idea. LaTeX is a typesetting language "intertwined with LaTeX commands". Since it has been around a long time, many "plugins" called *packages* are available to customize the layout and design for a wide range of uses.

If you are like me and had never used LaTeX before, learning this tool is all about research, trying out some ideas, reading some more, trying again and so on. You learn best by doing.

## Useful LaTeX Resources

Where to start? A fellow Canadian living here in Berlin told me to start by going to the <a href="http://tug.org/" target="_blank">TeX User Group (TUG)</a> site. Good advice.

At TUG, you can downloaded all the required software to set up a LaTeX publishing system on both MAC and Windows machines. As I wasn't sure which OS I would ultimately use, I set up LaTEX on both machines. The site has a _Getting Started_ page which I recommend reading. See <a href="https://tug.org/begin.html">Getting Started with TeX, LaTeX and Friends</a>

Some other useful resources include the _LaTeX Project Site_ (<a href="http://www.latex-project.org/">www.latex-project.org</a>), as is the _Comprehensive TeX Archive Network_ (<a href="http://ctan.org/">ctan.org</a>).

## Deconstructing a Simple LaTeX Document

In the Quick Start Guide, we entered a sample LaTeX document in a LaTeX editor then built this file to generate a pdf.

Let's now take a closer look at the structure of a very simple LaTeX file, the classic Hello World file.

```latex
\documentclass{article}
\begin{document}
Hello world!
\end{document}
```

When you write a LaTeX document you are essentially giving commands to the LaTeX typesetter how to treat the information on each line, or blocks of lines.

The first line in this example tells the compiler that what follows is a type of document of class *article*.

```latex
\documentclass{article}
```

 The compiler now knows what to expect and it has built-in macros to deal with this type of document (as well as many other types of LaTeX documents). It tells the compiler to use its *article* macros to build a layout and use the content.

After this command, you then need to tell the compiler that the document is beginning.

```latex
\begin{document}
```

Afterwards, you give the compiler the content of the document, which in this case is quite uninspiring.

```latex
Hello World!
```

Then you have to tell the compiler that the document is finished.

```latex
\end{document}
```
That's it!

Of course, for creating a technical document, much more detail is required. But these  elements form the basic structure of a simple LaTeX file.
