# Introduction to LaTeX and Zotero
## Why LaTeX?
### LaTeX Compared to Microsoft Word/Apple Pages/LibreOffice Writer/etc.
LaTeX is a text processor which is especially designed for larger texts and texts which should go towards printed output. Common word processors (MS Word, Apple Pages, Libre and OpenOffice, ...) do not prepare print-like documents in so far as these programs do not reflect the rules of professional printing which have been grown over centuries. These rules contain clear requirements for balancing page layouts, the amount of white space on pages, font-handling, etc. LaTeX is a sort of markup language (similar to html or markdown) which allows authors to concentrate on the structure of their texts and leave a professional layout to the software. The pros of LaTeX over Word or similar WYSIWYG editors are the following

- Print-ready output
- Formatting is done by the software, not by the user
- Authors can concentrate on the logical structure of their text
- Easy handling of citations, list of figures, and all other cross references
- Perfect typesetting of mathematical formulas
- Document can be easily split into different input files to facilitate team work

Of course, there are not only advantages so we list the cons here too

- No WYSIWYG
- A markup language must be learned
- A new paradigm in typesetting has to be learned

### A Final Word About Pronunciation
This is best explained by the author of LaTeX, Don Knuth:

English words like ‘technology’ stem from a Greek root beginning with the letters τεχ ...; and this same Greek word means art as well as technology. Hence the name TeX, which is an uppercase form of τεχ.

Insiders pronounce the χ of TeX as a Greek chi, not as an ‘x’, so that TeX rhymes with the word blecchhh. It’s the ‘ch’ sound in Scottish words like loch or German words like ach; it’s a Spanish ‘j’ and a Russian ‘kh’. When you say it correctly to your computer, the terminal may become slightly moist.

## Where to Download
LaTeX is available on all platforms. For Windows MiKTeX (http://miktex.org) in combination with TeXMaker (http://www.xm1math.net/texmaker/) is the most widely used software. MiKTeX is the LaTeX implementation for Windows and TeXMaker provides a nicer user interface to prepare LaTeX documents.

On Mac you use MacTeX and TeXShop. Similarly to Windows you need a LaTeX engine (which is MacTeX) and a front end/editor (which is TeXShop). When downloading MacTeX please take care that you use the full distribution and no smaller download.

Ubuntu provides LaTeX via its package management system. By typing the command apt-get install texlive into the terminal the installation of LaTeX should be done.

Direkt links to the download pages are as follows:

- MacTeX to be downloaded from [MacTeX](http://www.tug.org/mactex/)
- TeXShop to be downloaded from [TeXShop](http://pages.uoregon.edu/koch/texshop/obtaining.html)
- MiKTeX to be downloaded from [MiKTeX](https://miktex.org/download)
- TeXMaker can be downloaded from [TeXMaker](http://www.xm1math.net/texmaker/download.html)

When installing MiKTeX and TeXMaker on Windows, please take care that MiKTeX should be installed **BEFORE** TeXMaker.

## First Functional Test
After having downloaded the LaTeX package we should give it a first try. The procedure in LaTeX is as follows:

- Source code: The text and structural information you provide. Source code (also called LaTeX code) goes into tex-files (Files with the extension .tex)
- LaTeX: Generate a pretty print (mostly in pdf format) out of the source code. This step has different names. Some say "to LaTeX a file" some "to TeX a file" others "to typeset a file". Your choice as long as you pronounce it correctly ;-)
- Final document: In our case always pdf.

1. Open the [first LaTeXDocument](FirstLaTeXTest/FirstLaTeXTest.tex) in your LaTeX-Editor
1. LaTeX the file
1. When you were successfully typesetting the tex-file a number of further files can be found in your folder (aux, log, console, ...)
1. Open the pdf file and you should be able to see the final document
1. Change the author to your name and typeset again
1. Read the document and analyse the tex-file along the description given in the document
1. Add another section named "My Personal Remarks" to the document and list your remarks what you would like to have changed in this document to make it better understandable. If the document was perfect to you, simply add a sentence like "Thanks for the great explanation, I understood everything". Of course, your personal remarks can also be in German.
1. Do not worry if you are not pleased yet with the formatting. We will fix this in the online phase.
