# Workshop: Online Phase Part I: Zotero

## Fixing Last Issues
Everybody must be able to typeset the diploma thesis template


## Motivation
During project work it is quite normal to run into situations where external help is required. Most of the time in these situations an online search is done. With a bit of luck a solution can be found (*StackOverflow is our friend*) and this solution (or at least the idea of it) is applied to the own project.

This procedure is basically the same when working on a diploma project with one difference: When knowledge from external sources (web sites, books, articles, etc.) is taken we have to mention this later in the thesis. This is to make clear to the reader which parts of the thesis originally come from the author and which parts are taken from other sources.

Another point during project work is to save mental hooks of important steps during the course of the project. When it finally comes to write the thesis these hooks will clearly facilitate the writing process. For these two tasks Zotero can be of good help. We will start with a part which shows how to save references in the Zotero database and then we will show how to export these references into BibTeX to make it available for the thesis.

## Saving Project Results
### General Approach
Whenever you consult an online resource or you take an idea given in a book or paper you do the following

1. Adapt the solution found to the special needs of your project.
1. Try and test carefully whether the solution found is a real solution to your problem.
1. When it works, take a deep breath.
1. Add the source(s) you took for your solution to the Zotero database by simply clicking on the "Add to Zotero" Button in the browser.
1. Add tags and notes to your newly added entries using the Zotero Desktop Application.

### Practise
Go to different websites and add them to the database. Try

- Wikipedia
- Stack Overflow
- Website with meta data (e.g., Ray Wenderlich)
- GitHub
- Amazon
- YouTube
- PDF

and inspect the Zotero entries then.

## Exporting to BibTeX
Before exporting your database to BibTeX we have to check all Zotero entries whether they have at least the two following entries:

- **Author:** Change between single-field (organizations, Wikipedia, StackOverflow, etc.) and double-field authors (real person authors) entries to get export right.
- **Year of publication:** Every entry in the bibliography should at least have mentioned the year when it has been published. If this is not the case it is highly doubtful that this source is a very reliable one.

If these two entries are given for each entry in your Zotero database we are ready to export to a BibTeX library (`da_bibliography.bib`). Care must be taken that the option BibTeX is chosen (**not** BibLaTeX). Finally the result can be checked by opening the generated  file in a text editor.

How to further proceed with the BibTeX file to get it into the thesis is described in the next part of the workshop ([LaTeX](LaTeX.md)).
