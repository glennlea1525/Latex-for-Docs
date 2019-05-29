---
title: Using Input or Include Commands
description: In a root file, referencing chapter file can be done using either the include or the input commands
layout: single
categories: latex
---

When referencing external chapters to include them in the output stream while generating a LaTeX document, you can use either \input or \include.

The following provided an explanation of the difference between using the `\input{filename}` and `include{filename}`. The full text can be read <a href="https://tex.stackexchange.com/questions/246/when-should-i-use-input-vs-include">here</a>) on tex.stackexchange.com.

## \input Command

The `\input command imports the commands from filename.tex into the target file; it's equivalent to typing all the commands from filename.tex right into the current file where the \input line is.

### Syntax

```latex
\input{filename}
```
## \include Command

This essentially does a \clearpage before and after \input{filename}, together with some magic to switch to another .aux file, and omits the inclusion at all if you have an \includeonly without the filename in the argument. This is primarily useful when you have a big project on a slow computer; changing one of the include targets won't force you to regenerate the outputs of all the rest.

### Syntax

```latex
\include{filename}
```
