# Writing Chapters and Appendices

Chapters in LaTeX require specific commands and use section headings which are pulled out into the Table of Contents

Writing chapters are the bread and butter of technical writers. It is the content of the document. LaTeX is well served to produce very good content. Furthermore, it allows for individual chapters in the spirit of FrameMaker.


## Concepts, Tasks and Reference Materials

This topic will show the main elements that you will often use when writing a topic. Unlike DITA, you do not need to conform to a standard, although the rules for concepts, tasks and reference do apply.

Concept information should focus on describing general overview information. This is background information that may or may not be required to understand the tasks that a user needs to do with the software or hardware you are documenting.

Task chapters should be just that - tasks as procedures to accomplish a single operation on the software or hardware.

Reference material should be pulled out for quick access, such as API endpoints and so forth.

So, here are the most commonly used LaTeX elements you would use to write a chapter. It is not exhaustive, nor does it describe the many possibilities available.

## Chapter Identification Elements

Each chapter begins with the following elements:

```latex
\chapter{Overview}
\label{sec:Overview}
\index{overview}
```

The first line requires you to define the title of the chapter. This is used in the headers and in the Table of Contents.

The second line is used for cross-referencing to this chapter. It serves as a marker or anchor. The third line is used by the index.

## Section Headings

Creating a section head is quite easy. Second and third level headings are just as easy. Just use the following:

```latex
\section{heading text}
\subsection{heading text}
\subsubsection{heading text}
```

Three levels of headings are best. Any more and you may need to rewrite sections so they are at most third level deep. If you must, then just use a bolded paragraph for a fourth level heading.

## Paragraphs

Paragraphs are entered without markup tags. Adding a new paragraph requires a blank line between paragraphs.

```latex
This is the first paragraph about Road Runners.

This is the second paragraph about Road Runners.
```

## Comments

You can add comments to the .tex file as required using the % character.

```latex
% Add a comment using this character and LaTeX will ignore the rest of the current line.
```

## Paragraph Line Breaks

You can add a line break into text by adding \\ where you want to break the line. You can also use the following:

```latex
\newline
```

## Images

The `graphicx` pack­age builds upon the graph­ics pack­age by pro­vid­ing a key-value in­ter­face for op­tional ar­gu­ments to the `\in­clude­graph­ics` com­mand.

This in­ter­face pro­vides fa­cil­i­ties that go far be­yond what the graph­ics pack­age of­fers on its own. Do not use the older graphics package when using graphicx.

You first add the following to the stylesheet:

```latex
\usepackage{graphicx}
```

You then insert the image using the following syntax.

```latex
\includegraphics[width=10.91cm, height=2.33cm]{images/logo.png}\\[-1em]
```

You can resize the image or you can scale the image as follows:

```latex
[width=10.91cm, height=2.33cm]
[scale=1.75]
```

The `[-1em]` is a positioning element, which moves the image 1em to the left of the defined left margin. This is a page design issue.  

The file extension can be omitted, but I prefer to keep the entire filename, including the extension.

You can optionally use the `\graphicspath` command, but I had no need for it.

```latex
\graphicspath{ {images/} }
```

## Text Formatting: Emphasis, Bold and Underlining

To make text *bold*, use:

```latex
\textbf{Road Runner}
```

To make text _italicized_, use either:

```latex
\textit{ACME}
\emph{ACME}
```

To make text underlined, use:

```latex
\underline{Tunnel Ahead}
```

## Lists - Ordered and Unordered

When making an unordered list, you use `itemize`. When making an ordered list, you use `enumerate`.

The following is an example of an unordered list:

```latex
\begin{itemize}
\item \textbf{Body} - The thing that holds the fins in the right place.
\item \textbf{Fins} - The things that steer the tunafish in the sea.
\item
\end{itemize}
```

The following is an example of an ordered list:

```latex
\begin{enumerate}
\item Get a boat that you can use such as a rowboat or canoe.
\item Get a fishing rod.
\item Find where the tunafish are in the ocean.
\item Open can of tunafish that you remembered to bring with you and place it on the hook on the fishing rod.
\item Cast the line out into the sea and wait until a tunfish bites the hook.
\item Reel in the tunafish into the canoe.
\end{enumerate}
```

## Nested Lists

Nested lists are easy to make:

```latex
A Fish contains these parts:

\begin{enumerate}
\item \textbf{Body} - The thing that holds the fins in the right place.
     \begin{itemize}
     \item The fish body is the yummy part that you can eat.
     \item it also has lots of bones and stuff that you cannot eat.
     \item \textbf{Fins} - The things that steer the tunafish in the sea.
        \begin{itemize}
        \item The fins are sometimes sharp so be careful when cutting them off the fish.
        \item Do not eat them. Its all bone and skin.
        \end{itemize}
     \end{itemize}
\end{enumerate}
```

## Resuming an Interrupted List

I found it rather annoying that LaTeX didn't have an easy way of dealing with interrupted lists, until I learned this tip on StackOverflow.

I used the package `\enumitem` and used the `[resume]`` option on an enumarate scope to cause the LaTeX typesetter to continue numbering from the previous list. For example:

```latex
\documentclass{article}
\usepackage{enumitem}
\begin{document}</p>

\begin{enumerate}
    \item List item
    \item Another list item
\end{enumerate}</p>

A randomly inserted paragraph.

\begin{enumerate}[resume]
    \item Further item
    \item Final item
\end{enumerate}

\end{document}</p>
```

## Inserting Code Snippets

LaTeX provides a default command `verbatim` for inserting code. It ignores all text and commands within the environment and outputs the text in monospaced font.

```latex
\begin{verbatim}
    /* HelloWorld.java
    */

    public class HelloWorld
    {
        public static void main(String[] args) {
	        System.out.println("Hello World!");
        }
    }
\end{verbatim}
```

The `listings` package supports most common languages. To include this package, add the following line to the stylesheet.

```latex
\usepackage{listings}
```

Then you can add your code sample.

```latex
\begin{lstlisting}[language=java]
    /* HelloWorld.java
    */

    public class HelloWorld
    {
        public static void main(String[] args) {
        System.out.println("Hello World!");
       }
    }
\end{lstlisting}
```
