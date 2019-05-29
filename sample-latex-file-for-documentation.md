---
title: Sample LaTeX Root File
description: Orange juice is juice from oranges. It's made by squeezing oranges.
layout: single
categories: latex
---
<p>What we have here is a root LaTeX file that references a number of other files and gives the document a basic structure. The fun stuff has been placed in <em>include</em> files to make writing the document manageable. If you have used FrameMaker, you will see a pattern: the FrameMaker Book file works basically the same way as this LaTeX root file.</p>

<pre><code>\documentclass[a4paper,12pt,draft,twoside]{book}
\usepackage{styles/mystyles}

\begin{document}

\frontmatter

\include{tex/title}

\tableofcontents

\mainmatter

\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}

\backmatter

\end{document}
</code></pre>

<p>So, let's go through this file section by section.</p>

<h4>Defining the Document Class</h4>

<p>The first line tells the LaTeX generator the type of document it is about to generate (or typeset) and what styles are to be used.</p>

<pre><code>\documentclass[a4paper,12pt,draft,twoside]{book}
</code></pre>

<p>All these elements are defined in separate class files. More about these classes later.</p>

<p>The \documentclass line defines the type of document you intend to create. This document will be printed (or output to pdf) in A4 format. The base font will be 12 points, although this can be modified in the document. It is marked as draft initially. And it will be printed on both sides.</p>

<p>The word <em>book</em> within the curly braces tells the typesetter to use the Book class. This is a set of predefined outputting instructions, which in this case has functionality that can handle large multi-chapter documents, which manuals tend to be.</p>

<p><em>Note:</em> Another option is using the <em>memoir</em> class, which offers a useful alternative.</p>

<h4>Externally Referencing the Stylesheet</h4>

<p>Following the document class definition, you tell the typesetting engine to use the styles defined in an external document called <em>mystyles</em> located in a directory below the root called <em>styles</em>.</p>

<pre><code>\usepackage{styles/mystyles}
</code></pre>

<p><em>mystyles</em> is a stylesheet in which I have defined all the styles that will be used in this document. This allows me to update the stylesheet without having to worry about finding the styles within the root file (the alternate location for styles).</p>

<h4>Beginning the Document</h4>

<p>Like the body tag in HTML, the actual content follows this tag:</p>

<pre><code>\begin{document}
</code></pre>

<p>It tells the typesetter that what follows is the document. The document section is divided into three subsections: <em>frontmatter</em>, <em>mainmatter</em> and <em>backmatter</em>.</p>

<h4>Defining a Title Page</h4>

<p>In the <strong>frontmatter</strong> section, I included a title page, although the book class has a default title page which can be referred to simply as <strong>titlepage</strong>. In this section I want my table of contents as well, which is automatically generated during output.</p>

<pre><code>\frontmatter

\include{tex/title}

\tableofcontents
</code></pre>

<h4>Indicating the Document Body</h4>

<p>The document itself, namely, the contents, is contained within the <em>mainmatter</em> section.</p>

<pre><code>\mainmatter
</code></pre>

<p>To keep this simple and to allow chapters to be toggled off or on, all content is placed in external files in a subdirectory called <em>tex</em>. The \include command is used to tell the typesetter to go locate the file within the curly braces and generate the output and include it at the location in the list of includes.</p>

<pre><code>\include{tex/preface}
\include{tex/intro}
\include{tex/chap01}
\include{tex/chap02}
\include{tex/summary}
</code></pre>

<p><em>Note: You would also define your headers and footers here, but I excluded them in this example to keep it simple. I will get to them in due time. I also included an appendix, but is not shown in my example.</em></p>

<p>A <em>backmatter</em> section is also included, which typically includes the Index.</p>

<pre><code>\backmatter
</code></pre>

<h4>Closing the Document</h4>

<p>You need to tell the typesetter when the document is complete, that is, there is no more files to generate. In other words, you need to close your document, as in all tagged files.</p>

<pre><code>\end{document}
</code></pre>

<p>This simple command indicates the end of the document and go ahead and generate the output.</p>

<p>We will get into more detail in an upcoming post.</p>
