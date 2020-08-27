---
layout: page
---

# Text based projects

* TOC
{:toc}

This documentation is for text based digital editions. We can define what we mean by that a little more fully, but it mostly means that the project concerns itself with collecting, annotating, presenting, or analyzing textual documents (rather than, say, spreadsheets or databases).

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
| --- | --- | --- | --- | --- |
| Text | .txt |
 |
 | Text that does not need to be displayed to the user, i.e. it will be primarily used for text analysis or other computational methods |
| Markdown | .md (preferred) .markdown |
 | HTML | Text that will be displayed to the user and does not need advanced formatting such as centering text or marking specific places or people |
| HTML | .html (preferred) .htm | TEI Markdown |
 | The display format for the web, HTML will primarily be used as an output format |
| TEI | .xml | Markdown | HTML | Text that will benefit from a more rich markup, such as items with embedded metadata or editions that would like to have advanced formatting for their display. |

## Edition Software

In order to create a text based edition, we will lean on a few pieces of software to do the job. As stated above, this list is not all inclusive - as we work on editions we will add to this list and will consider software as needed for project features.

### Datura

This software from the Center for Digital Research in the Humanities will be used to transform formats from one to the other and to compile metadata as needed.

[https://github.com/CDRH/datura/](https://github.com/CDRH/datura/)

### Jekyll

Jekyll is a static site creation software that is integrated with GitHub. The normal use of this software is to use it to create a website previewing locally and then &quot;building&quot; the project into static HTML files that can be served from anywhere. When used on GitHub, the build happens automatically when a change is uploaded (this can sometimes take a minute or two).

[https://jekyllrb.com/](https://jekyllrb.com/)

[Add: GitHub?]

## File Creation and Naming

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

## Workflow

TBD, fill in with process of working on a textual edition from start to finish

## Edition Creation

[placeholder, this will be a separate doc]