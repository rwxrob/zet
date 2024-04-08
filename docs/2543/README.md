# Moving everything to AsciiDoc

Update: Monday, April 8, 2024, 10:07:28AM EDT

As great as AsciiDoc is, most of the writing I do (and everyone else does) is not for publishing. Therefore, it seems to make more sense to continue to do everything in basic, GFM, or PFM and only convert to AsciiDoc when needed for publishing. I discovered this after many of hours researching the options to have a book and website be from the same content in both markdown and AsciiDoc. The single biggest distinguishing factor was lack of searchability with the AsciiDoc website generators. Lara.js is an option, but clunky and problematic compared to the built-in support for what has become the industry standard: MkDocs.

----

I first took a serious look at AsciiDoc when Kris Nova decided to write her book in it. She obviously knew about Markdown but after a lot of research went with AsciiDoc instead. After reading just a simple overview of how it works I completely understand why.

I've been working with Markdown for KEG and other stuff for over 10 years. I even created my own PEG grammars to isolate the syntax of Markdown to only the stuff I want to allow. But all this time (since 2013) asciidoc has existed. It was born out of the frustration with Markdown being so—umm—stupid. Markdown might be the standard out there, but it has always suffered from being something invented late one Sunday night to help Gruber convert his emails into blog posts. The asciidoc language was conceived primarily as a syntax for formal publishing without getting in the way of writing (like Markdown). All that extensions that Pandoc-Flavored Markdown has added are completely unnecessary. The amazing work JGM did to get CommonMark adopted by even a few companies so there is some agreement simple doesn't matter in the asciidoc world. The community is already centered and focused and committed to never fracturing the syntax. In fact, syntax expansion is a core part of the asciidoc specification itself.

In short, asciidoc is for smart people. Markdown is big ugly boomer tech that needs to just die because it will *never* achieve the level of specificity and sustainability that asciidoc achieved on the first day it was conceived.

## Pros

* Specific and clear without lots of variations
* Commonly used to publish books as well as searchable web sites
* Built-in, first-class support for extensions
* Strongly specified and governed

## Cons

* Yet another language to learn
* Relatively new (created in 2013)
* Less support (although GitHub does support)
* No GitHub pages automatic rendering (by default, but addable)

## Related

* How to write your book with AsciiDoc --- Liran Tal  
  <https://lirantal.com/blog/how-to-write-your-book-with-asciidoc/>
* Writing a Book in Markdown with Version Control \| A Mild Voice of Reason  
  <https://www.jegillikin.com/2018/06/writing-a-book-in-asciidoc-with-version-control/>
* test-builds - Read the Docs  
  <https://beta.readthedocs.org/projects/test-builds/builds/21989207/#203831360--7>
* Main Page :: Antora Demo on ReadTheDocs  
  <https://example-antora-basic.readthedocs.io/en/latest/main/index.html>
* <https://docs.readthedocs.io/en/stable/examples.html>
