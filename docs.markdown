---
layout: page
title: Text-Based Projects
permalink: /docs
---

**This page is a work in progress**

* TOC {:toc}

This documentation is for text-based digital editions. We can define what we mean by that a little more fully, but it mostly means that the project concerns itself with collecting, annotating, presenting, or analyzing textual documents (rather than, say, spreadsheets or databases).

Data projects will likely be handled on a one by one basis with documentation created as we go.

## Text Formats

The main text formats we will use are as follows:

### Text (.txt)

Plain text with **no formatting.** no bold, no italic, etc.

Plain text will come in two main flavors: Dirty OCR and clean text. Many projects use Optical Character Recognition (OCR) to get text out of printed materials - this text is considered &quot;dirty&quot; because no one has gone through and compared the text to the original, and errors in computer transcription will likely be abundant. A clean transcription is achieved when a person (often 2 or three!) have gone through and made corrections.

If a human is going through and making corrections anyway, it might be a good idea to go ahead and mark up the text in markdown - that way you can capture things like headers and italics without having to go back to the source text again later.

### Markdown (.md or .markdown)

This is a newer format that nonetheless has good adoption. Markdown is a simplified text notation meant to be transformed into HTML, and mostly mimics standard HTML elements. You can find information about markdown here: [https://www.markdownguide.org/](https://www.markdownguide.org/). This project will also use the extended syntax at [https://www.markdownguide.org/extended-syntax/](https://www.markdownguide.org/extended-syntax/).

Markdown is rendered by default in github and in github issues.

Even with the extended syntax, there are some limitations to markdown: for instance, there is no way to change text alignment or add containers to aid with decoration.

### HTML (.html, .htm)

HTML is the language of the web. It is a very basic and flexible framework for marking up a document.

For the purposes of this project, we will likely usually arrive at HTML by transforming a document from markdown or from simple TEI. If editors would like to encode documents directly in HTML, we can advise on best practices.

[Note: though at some point we may want to consider coming up with an HTML5 schema that conforms to TEI Simple if we really want people to be able to encode IN html]

### TEI (.xml)

TEI is a standardized way of marking up text documents with good documentation and support. You can find guidelines at [https://tei-c.org/](https://tei-c.org/).

TEI aims to be a standardized way to mark up _all_ textual documents, so it can be quite complex. Because of that, we are advising any projects that do not need advanced features to use TEI Simple, which is a limited tag and ruleset that conforms to TEI rules but simplifies for the most common use cases such as marking up a manuscript. You can find more information here: [http://teic.github.io/TEI-Simple/](http://teic.github.io/TEI-Simple/)

When a document is marked up with TEI (Simple or otherwise) it will be transformed into HTML for display using Datura (see below), or else will be displayed using one of the many tools for this such as CETEIcean (https://github.com/TEIC/CETEIcean) or TEI Boilerplate (http://dcl.ils.indiana.edu/teibp/).

### Text format comparison chart

| **Format** | **Extensions** | **From** | **To** | **Uses** |
| ---        | ---            | --- | --- | --- |
| Text       | .txt           |     |  Markdown    | Text that does not need to be displayed to the user, i.e. it will be primarily used for text analysis or other computational methods |
| Markdown   | .md (preferred) .markdown | | HTML     | Text that will be displayed to the user and does not need advanced formatting such as centering text or marking specific places or people |
| HTML | .html (preferred) or .htm | TEI Markdown | | The display format for the web, HTML will primarily be used as an output format |
| TEI | .xml | Markdown | HTML | Text that will benefit from a more rich markup, such as items with embedded metadata or editions that would like to have advanced formatting for their display. |

# Intro to Markdown
Some basic terminology: 

**Characters**

In computing terms, a character is any letter, number, space, punctuation mark, or symbol. A is a character; 9 is a character; ? is a character. "Character" became a familiar term for many denizens of social media thanks to the "character limit," that is, the max number of characters (letters, numbers, line breaks, symbols, etc.) allowed in a single social media post. Lookin' at you, Twitter (RIP).

**Syntax**

You're probably familiar with the term "syntax" as it is used in linguistics: rules that govern how words and phrases are arranged to create well-formed sentences. Similarly, in coding and programming languages, "syntax" refers to the arrangement of words, symbols, and other characters to create well-formed code. If, in your code, the syntax is correct, that piece of code will function and display correctly in your end result. If your syntax is incorrect, it usually will display incorrectly, function incorrectly, or not display or function at all. If you hear someone say "Check your syntax," they mean proofread your code. Sometimes all it takes is missing a space or a symbol in your code.

Fun fact: as humans, we can be pretty loosey goosey with syntax in some contexts, of course (take, for example, my frequent failure to correct sentences I end prepositions with), while in other situations we might be very strict about correct syntax. Similarly, some programming languages are very strict when it comes to syntax, while others are a little more lenient.

**Wrap/Wrapping**

When we say to wrap something with something else, like "wrap _x_ with _y_" we mean to put one _y_ before and after _x_. It's like you've made an _x_ sandwich, and _y_ is the bread. For example, if I were to "wrap x in double asterisks," I would type `**x**`.

## Markdown
The [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/) from markdownguide.org is a great page to have up while you are transcribing and editing your Markdown files. It's a quick-reference list of all the ways you can format things in Markdown, from bold and italics to footnotes and images. Rather than duplicate the excellent guides that accompany the Cheat Sheet here, we provide links and some brief annotations for things commonly used in digital editions. 

### Basic Markdown 

[Paragraphs]
Perhaps the most straightforward element in this list, paragraphs are formed simply by separating two lines of text with a blank line.

```
This is my first paragraph.

This is my second paragraph.
```

**[Bold text and Italicized text]**
Both asterisks (`*`) and underscores (`_`) can be used to make words or phrases bold and/or italicized. To italicize text, wrap it in single underscores (`_this_` makes _this_) or single asterisks (`*this*` makes *this*). To bold text, wrap it in _double_ underscores or _double_ asterisks (`**this**` makes **this**, and `__this__` makes __this__).

**We recommend choosing one for bold, and the other for italics.** We find that this makes it easier to visually differentiate between them when editing or proofreading Markdown file. The author of this documentation always uses the underscore for italics (like `_this_`) and double asterisks for bold text (like `**this**`).

[Headings](https://www.markdownguide.org/basic-syntax/#headings). 

**[Line breaks](https://www.markdownguide.org/basic-syntax/#line-breaks)**
Use paragraphs when you can. There will be cases—particularly with poetry—where you are, in fact, transcribing line breaks rather than paragraphs, and don't want the space that comes between paragraphs. 

**[Tables](https://www.markdownguide.org/extended-syntax/#tables)**
Tables are not the easiest to create and edit in Markdown. If you need to add a table, it's often easier to copy and paste an example table rather than create one from scratch.


## Other useful things you can add to your GitHub pages site with Markdown

### Table of Contents

Github Pages will automatically display a Table of Contents to your file if you include the code `{:toc}`. The Table of Contents will link to headings in your document, so make sure to use proper hierarchy/nesting of headings.

### Images

### Tables

### Superscript

**Before you use this, read the documentation on footnotes.** In Markdown, creating a footnote (e.g. `This sentence has a relevant footnote.[ch1-ref1]`) automatically adds the superscript footnote number for you. You do not need to add the extra symbols described here.

To make a character superscript, wrap it in caret symbols.

# Edition Software

In order to create a text based edition, we will lean on a few pieces of software to do the job. As stated above, this list is not all inclusive - as we work on editions we will add to this list and will consider software as needed for project features.

## GitHub

### What is Git, and what is GitHub?
GitHub is based on [**git**](https://docs.github.com/en/get-started/using-git/about-git), a system that intelligently tracks changes in files. As people and teams collaborate on projects together, any earlier version of the project can be recovered at any time. Using the git system makes it easier to see a timeline of the changes, decisions, and progress you've made on your project. Looking back at a project's history using Git can tell you:

    Which changes were made?
    Who made the changes?
    When were the changes made?
    Why were changes needed?

A project in Git is called a **repository**, and it is where all your project's files and folder will be stored. **GitHub** is a cloud-based hosting service that allows you to store your GitHub repository—with all of Git's version control and tracking features—on the web, either privately or publicly.

When you begin a project that will be in the Recovery Hub framework, we will create a repository for your project on GitHub - more specifically, under the umbrella of the Recovery Hub's GitHub "Organization." You can see the list of repositories in the Recovery Hub GitHub Organization at https://github.com/recoveryhub/.


### Why use GitHub?
- Versioning - what does "versioning" mean, and what does it look like in practice/in GitHub? Maybe have a section called "Looking back at past versions of a file"

### What is a repo?

# Editing files on your computer vs. in your browser
Differences: save (command+s or control+s, I think it's automatic in the browser)

### "Saving" your changes - i.e. "Committing" your changes

[ref1] Maksi, Mark. "No Git, No Problem: The Absolute Beginner's Guide to GitHub." 15 May 2024. Accessed 19 Jul 2024. <https://favtutor.com/articles/github-beginners-guide/>

## Datura

This software from the Center for Digital Research in the Humanities will be used to transform formats from one to the other and to compile metadata as needed.

[https://github.com/CDRH/datura/](https://github.com/CDRH/datura/)

## Jekyll

Jekyll is a static site creation software that is integrated with GitHub. The normal use of this software is to use it to create a website previewing locally and then &quot;building&quot; the project into static HTML files that can be served from anywhere. When used on GitHub, the build happens automatically when a change is uploaded (this can sometimes take a minute or two).

[https://jekyllrb.com/](https://jekyllrb.com/)


# File Creation and Naming

When an edition is created a naming scheme will be defined. Depending on the complexity of the project there may be more to it than the following, but this serves as a basis.

Every project will have a project &quot;longname,&quot;a &quot;shortname,&quot; and a file prefix

Sample Edition Name: Edition One

Sample Edition Shortname: edition-one

Sample Edition file prefix: edone

- The long name can be anything you choose. [Note: we may want to give more guidance]
- The shortname can only contain upper and lowercase letters, underscores ( \_ ) and dashes ( - ). By convention we primarily use dashes.
- The file prefix should ideally be 6 characters or less.

### Text Files

Text files should begin with the file prefix and then have a padded number (the padding length can be variable, but I usually default to 5 spaces, i.e. 00001, unless there will be more than 99,999 items)

edone.00001.xml

edone.00002.xml

etc.

If there are multiple file formats, i.e. some are in markdown and some are in TEI, it is recommended you don&#39;t use the same number for each to reduce the potential for overwriting when transforming to HTML

| **Wrong** | **Right** |
| --- | --- |
| edone.00001.xmledone.00001.md | edone.00001.xmledone.50001.md or edone.00001.xmledone.00002.md |

Note that it does not matter what numbers you choose.

You may optionally decided to add another prefix to the filename to further separate files:

For instance, if you were encoding both books and letters, you might have filenames like:

edone.bks00001.xml

edone.let00001.xml

### Image Files

Image files connected to a text file should use the text file name as a base. For instance, if you have a file named:

edone.bks00001.xml

you might have images named:

edone.bks00001.001.xml

edone.bks00001.002.xml

edone.bks00001.002.xml

etc.

If you have other image files you can name them sequentially as needed, i.e.

edone.00001.jpg

But be sure to watch for potential conflicts with text files.

Any standalone images files should have either a corresponding CSV that notes metadata, or else metadata embedded in the image file itself.

When creating image files, rename all images in the preservation format (.tif , .jp2, .png) BEFORE creating derivative jpegs!

[Note: We can add more on image processing here later - I&#39;m not sure how in depth we want to get. I think for our purposes we should recommend, say, a 2000 px jpeg and recommend the preservation format is zipped and deposited somewhere like humanities commons]

## Edition Data Storage

The edition data storage is based on what the CDRH has created for Datura.

Note the use of the shortname &quot;edition-one&quot; in the folder naming and the file prefix on filenames

- data\_edition-one
  - config
    - yml
  - scripts
    - verrides
      - [project specific scripts]
  - source
    - drafts
      - [output format]
    - [output formats, for example:]
    - tei
      - 00001.xml
    - markdown
      - 00002.md
    - text
      - 00003.txt
  - utput
    - production
      - html
        - 00001.html
  - files
    - assets
      - style.css
    - images
      - 00001.001.jpg
      - 00001.002.jpg

Note that output is reserved strictly for script generated formats - do not edit items in this folder as they will be overwritten next time the script is run. All human editable files should be added to /source
