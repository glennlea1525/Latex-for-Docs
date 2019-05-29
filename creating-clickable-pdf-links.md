# Creating Hypertext Links

When generating a PDF, you create clickable links using the hyperref package.

When you generate a pdf version of a user guide, you want cross-references within the document to be clickable. Otherwise, why bother making them. Using the `\hyperref` package allows this.

The `\hyperref` command can be customizable. For details, Google is your friend.


## Using the hyperref Package

You need to add the following command to your stylesheet to turn internal references into hyperlinks, including table of contents, list of figures/tables and indexes.

```latex
%\usepackage{hyperref}
\usepackage[hidelinks]{hyperref}
```
I commented out the first command and uncommented out the second command, which includes an option. The option `hidelinks` removes color and border from the link. In printed documents, an underline is unsuitable.

Having multiple commands allows me to toggle easily between output for print and output for online use.

## Inserting External References

You can insert a link into a document using the following command to display the link using the standard document font.

```latex
\href{<url>}{<text to display>}
```
The first parameter is the url to link to, the second is the text to display, as in the following command.

```latex
\href{http://www.glennjlea.ca}{My Website}
```
If you want mono-spaced font for the link, you can use this command.

```latex
\url{http://www.glennjlea.ca}.
```

## Inserting an Email Address

You can insert an email address into a document using this command.

```latex
\href{mailto:my_address@glennjlea.ca}{my\_address@glennjlea.ca}
```

## Inserting a Link to a Local File

If you need to open a local file, which is always troublesome if the file is not there, you can use this command.

```latex
\href{run:/path/to/my/file.ext}{text displayed}
```

## Inserting an Anchor and Linking to the Anchor

This is what you need to insert a cross-reference to an anchor somewhere in your document.

First, you need to insert an anchor.

```latex
\hypertarget{label}{target caption}
```

Then you need to link to it.

```latex
\hyperlink{label}{link caption}
```
