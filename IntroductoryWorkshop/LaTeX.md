# Workshop: Online Phase Part II: LaTeX

## Adding Title and Chapters
Open the file [Globals.tex](../Templates/LaTeX/Globals.tex) and change the data into the one fitting to your thesis. If you do not need an entry put it under comment (using %) or delete it. Go back to [Main.tex](../Templates/LaTeX/Main.tex) and LaTeX the project again.

## Multi-Language Documents
The diploma thesis is a multi-language document (the abstract has to be written in German and English). The language settings in LaTeX are pretty important because

- Predefined text is printed in the active language (Inhaltsverzeichnis vs. Table of Content, Abstract vs Zusammenfassung, etc.)
- Hyphenation is done according to the rules of the active language
How to set up a multi-language document and how to select the active language is described here

### Loading the Package and Selecting the Active Language
Multi language support is done via the bable package. With `\usepackage[german, english]{bable}`
the package is loaded. The options within the square brackets (german, english) list the languages used in your document. The last language in the list is the active language (english).

### Changing the language
`\selectlanguage{german}` switches the active language to german. For very small portions of text in another language it is recommended to use the command

```
\foreignlanguage{german}{Text in deutscher Sprache}
```
or for a bit longer texts (abstracts) it can be useful to use the otherlanguage environment:
```

\begin{otherlanguage}{german}
   \begin{abstract}
      In dieser Diplomarbeit geht es um ...
   \end{abstract}
\end{otherlanguage}
```
## Cross References
Referring to other places in text (other pages, chapters, images, tables) is part of a good writing style. This is explained here. Citing and handling the bibliography, however, will be part of a later section.

### Adding Labels
One can add labels to any part on their text by simply typing `\label{some-id}`.
Normally labels are attached to chapters, sections, images, tables. It is recommended to commit to some naming convention for labels. Normally one would add a prefix. Here are some examples:

- `\label{cha:introduction}`: label for a chapter called "Introduction"
- `\label{sec:goal}`: label for a section, subsection, or subsubsection "Goal"
- `\label{img:main-process}`: label for an image
- `\label{tab:results}`: label for a table

### Referring to labels
If one wants to refer to a label (say `cha:introduction`) simply write as follows:

```
As already described in chapter~\ref{cha:introduction} we have to ...
```
Note the tilde (~) between `chapter` and `\ref`. This describes a *non-breaking space* which means that LaTeX takes care that no line, page, column break happens between the word "chapter" and the number of the chapter.

If one wants to refer to the page only and not to a specific chapter, section, image, whatsoever this is possible via the command `\pageref{cha:introduction}`.

### Undefined References
When adding a new label or reference it is recommended to LaTeX the document immediately to see whether the reference has gone right. If not, one will face an "Undefined reference warning" in the output log. Watch out for these.

Under special circumstances it is necessary to LaTeX the document twice after entering a new label and a reference to it. This happens when a reference is added to an also newly added label which occurs in the text after the reference. Also you did everything right, an "Undefined reference" warning pops up in the first LaTeX run but when typesetting again this warning should vanish.

Reason: LaTeX works in the form of a single pass compiler and maintains its cross references in the aux files. If labels occur after a reference and both have been introduced without typesetting in the meanwhile the newly added label is not yet in the aux file. So LaTeX needs a second run the get cross-reference right.

## Floating Bodies
Floating bodies are the general term for images and tables (sometimes algorithms). In scientific documents these types of text are often floating outside the "normal" text flow (remember again html with the css floating property) and  placed somewhere on top or bottom of the page. How LaTeX supports this is described here.

### Images
Images are kept within the figure environment:

```
\begin{figure}
   \begin{center}
	\includegraphics[scale=.5]{path/to/image.jpg}
   \end{center}
   \caption{Don Knuth, the inventor of \TeX}
   \label{fig:sample}
\end{figure}
```

The image itself is included using the \includegraphics command. Note the \caption and the \label command which allows you to describe the content of the image briefly and to refer to the image out of the normal text flow, respectively.

### Tables
Tables are kept within the table environment

```
\begin{table}
	\begin{center}
	   \begin{tabular}{|l|r|}
		\hline
		Body type & Floats \\
		\hline
		Image & Always \\
		\hline
		Table & Always \\
		\hline
		Algorithm & Sometimes \\
		\hline
	   \end{tabular}
	\end{center}
	\caption{Different types of floating bodies}
	\label{tab:types-of-floating-bodies}
\end{table}
```
One has to distinguish between the environment holding the floating body (table) and the table itself (tabular). The table environment is analogous to the figure environment.

More interesting is the tabular environment to describe the table itself. The second argument with the upright bars (`|`) and the `l`s and `r`s indicate the alignment of each column of the cell. The upright bar says that we want to have a line between the columns. The \hline says that a horizontal line is required between two rows. In the content of one row each cell is separated by an ampersand (`&`) and each table row is finished by a double backslash (`\\`).

### List of Figures and List of Tables
It is required to have a list of figures and list of tables at the end of the diploma thesis. This is done by simply adding the commands \listoffigures and \listoftables into your tex-file at the place where these lists are required. The template has these commands already properly placed.

## Citation and Bibliography
### Adding a Citation to your Diploma Thesis
When checking the BibTeX file with a text editor it can be seen that each entry is labelled with its basic type (book, article, etc.) and then, within curly braces the data describing the entry is given.

```
@book{knuth_texbook_1984,
	address = {Reading, Mass},
	edition = {First},
	title = {The {TeXbook}},
	isbn = {978-0-201-13448-3},
	abstract = {This is the definitive and complete user manual to the TeX computerized typesetting system. TeX software offers both writers and publishers the opportunity to produce technical text, with the speed and efficiency of a computer system.},
	language = {English},
	publisher = {Addison-Wesley Professional},
	author = {Knuth, Donald E.},
	month = jan,
	year = {1984}
}
```

One can also see that all data is given in key value pairs separated by an equals sign (`=`). There is only one exception to this, namely the first field which is the key that is used to refer to the entry via the cite command. Example:

```
\cite{knuth_texbook_1984}
```
This command adds a reference (placed within square brackets) to the bibliography part of your thesis.

### Adding a List of References to your Diploma Thesis
In the template's `Main.tex` the commands

```
\bibliography{my_bibliography}{}
\bibliographystyle{alphaurl}
```
are responsible to generate a list of external resources (Bibliography) referenced within the thesis.

Adding an entry to the Bibliography which is not directly used in your thesis is also possible by writing the command `\nocite{bibtex-key}`. The entry with the key `bibtex-key` is added to the bibliography without getting a reference to it inside the text.

### Typesetting with BibTeX Entries
Since BibTeX should only pick up the entries of your BibTeX database which are really used in the thesis the following steps have to be done:

1. LaTeX the thesis: aux files are updated but "Undefined references" are found
1. BibTeX the thesis: bbl file is generated with only the needed entries of the bib file
1. LaTeX the thesis again (maybe twice): Bibliography is added to the thesis

Of course, these steps only have to be done if a new bibliography entry comes into the thesis.

### German Bib Style

A German bib style is *dinat* (`\bibliographystyle{dinat}`). To make this work correctly you additionally have to include the *natbib* package (`\usepackage{natbib}`).

## Online Resources
If you need help concerning LaTeX there is one great online resource, namely [https://en.wikibooks.org/wiki/LaTeX](https://en.wikibooks.org/wiki/LaTeX). Most of the time if you google a LaTeX question you will anyway get links to this page.

The [final part](Organizational.md) of the workshop deals with organizational stuff.
