# MkDocs seems best for most work documentation

The MkDocs designers have way more common-sense than those who designed the Hugo layout.

>  Many repository hosting sites provide special treatment for README files by displaying the contents of the README file when browsing the contents of a directory. Therefore, MkDocs will allow you to name your index pages as README.md instead of index.md. In that way, when users are browsing your source code, the repository host can display the index page of that directory as it is a README file. However, when MkDocs renders your site, the file will be renamed to index.html so that the server will serve it as a proper index file. If both an index.md file and a README.md file are found in the same directory, then the index.md file is used and the README.md file is ignored.

This works instantly with *any* standard GitHub repo that has been used for documentation already by a team.

MkDocs also follows an absolutely inspired algorithm for identifying the title:

       The "title" to use for the document.
       MkDocs will attempt to determine the title of a document in the following ways, in
       order:
         1. A title defined in the nav configuration setting for a document.
         2. A title defined in the title meta-data key of a document.
         3. A level 1 Markdown header on the first line of the document body. Please note that
            Setext-style headers are not supported.
         4. The filename of a document.
       Upon finding a title for a page, MkDoc does not continue checking any additional
       sources in the above list.

It even makes me love the developers more for throwing out `Setext` entirely.

* It's drop-dead simple to setup (much easier than Hugo)
* The source is easy to grok (well-written Python, as opposed to poorly-written Go)
* It uses `index.md` instead of `_index.md`
* It uses a saner documentation format and organization
