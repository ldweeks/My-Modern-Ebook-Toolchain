---
title: Lucas Weeks' E-Book Toolchain
---

--------------

# Notes for the future

When you get down to the section on the process, you'll see that I have a lot of work to do. I basically have decided that I want to use markdown as the starting point, and that's it. There are many hurdles to overcome. Here are the next steps:

- My vision for ebook curation and production depends on volunteers, and it depends on volunteers who are getting feedback. This is why a documentation-style page for each book is necessary on a website. It allows 1) volunteers to get immediate feedback on a section they've worked on, and 2) it gives others the ability to read and give suggestions. So, now, I need to figure out how to go from markdown files to website.
- TO DO:
  - Figure out the design of the website. For it to be working at a minimum, what features does it need?
  - Where will the site be hosted?
  - Figure out the best format for the Markdown file(s) to take. Single or multiple? Problematic kinds of tags? Consider all the outputs.

I think it's best to focus on my needs initially, and then to add others in if I get anywhere.

----------------

I spent a great deal of time in the past 24 hours thinking carefully about the process of producing books that will be transformed into a variety of different formats. Here are my thoughts as of 8/30/2018:

## I want to stick with Markdown. Why?

- It's simple to understand and write, even for non-technical writers.
- It has widespread adoption.
- It has good support from Pandoc.
- A potential negative is that Markdown has 20+ varieties, and so we could run into strange incompatibilities. To mitigate this, I think we choose [CommonMark](https://commonmark.org) and stick with it.

Someone might legitimately ask why we wouldn't use Microsoft Word as a starting point for each book and use that file to create the different versions. Isn't that a standard, too? Aren't people very familiar with it? It's a good question, and deserves a good response.

And my main response, leaving aside all my techie weirdness, is that the best way to clean up old books that have been OCR'ed is to work through them in a text editor. Microsoft Word, and other editors like it, are 1) set up for printed documents, primarily, and 2) encourage the user to add formatting, often without the user even knowing or understanding that they are doing it. So Markdown gives us a nice, clean a copy of the document that can easily be turned into other formats. Those, in turn, can then be modified as their medium requires.

## The process:

1. Edit and prepare books using CommonMark.
2. Export books in the following formats:
  - html
  - ePub
  - docx
  - Amazon

------------------

## Important Resources

- [Pandoc](https://pandoc.org)
- [CommonMark](https://commonmark.org)
- The folks over at [Standard Ebooks](https://standardebooks.org) are making high-quality ebooks, and it's a great resource. We will need to develop our own typography manual, and we may want to borrow a lot from [theirs](https://standardebooks.org/contribute/typography).
- Great write-up [here](https://medium.com/programmers-developers/building-books-with-markdown-using-pandoc-f0d19df7b2ca) on how to turn Markdown into a great epub. Github repo [here](https://github.com/johnpaulada/pandoc-markdown-book-template). This is really great because I'm pretty confident about just using this markdown format - single file for the entire book.
  - This is the money line: `pandoc -S --toc --epub-embed-font='fonts/*.ttf' -o book.epub metadata.txt contents.markdown`. It does everything you need in a pretty simple pandoc command. Next, I need to figure out how to run that same command for an html file and a docx file.
