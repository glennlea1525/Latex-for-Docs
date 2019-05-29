# Generating Output from a LaTeX File

After creating a LaTeX file, It needs to be built using the TeX distribution to generate an output PDF file.

Before we start actually working with the output from the converted PDF file as described in the previoius topic, lets look at how to generate an output file from a LaTeX file.

**To build a LaTeX file**

1. Type the following in a LaTeX editor and save the file as `HelloWorld.tex` in a convenient location on your PC or MAC.

        \documentclass{article}
        \begin{document}
        \title{Title of Document}
        \author{Your Name}
        \date{\today}
        \maketitle
        \tableofcontents
        \section{Section Head}
        Hello, world!
        \section{Second Section Head}
        This is the last thing I am going to say here!
        \end{document}

2. Build the LaTeX file. You can do this on the command line or in a LaTeX editor such as TeXworks. In TeXworks, for example, select the build option *pdfLaTeX+MakeIndex+BibTex* from the *Build* menu, then click *Build* (the arrow next to the dropdown menu). Alternately, open a terminal (MAC) or Command Prompt (Windows) and change to the directory where you saved the file. Then run the following command **twice** to build the file and to generate a table of contents:

        pdflatex HelloWorld.tex
        pdflatex HelloWorld.tex

3. In the directory containing `HelloWorld.tex` you will find a whole bunch of new files in there. For now, find the file `HelloWorld.pdf`and open it in a pdf viewer.

<img src="/assets/images/latex/hello-world.png" alt="LaTeX document with table of contents" style="width:583px;height:929px;">
<figcaption>LaTeX document with table of contents</figcaption>
