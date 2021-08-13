# ZettelMark: Raster Image Figures

Only a single raster image is allowed in any single zettel, such zettels
are known as *figure zettels* and don't have any parallel in Luhmann's
original Zettelkasten method (although I'm sure he might have considered
it had he had a greater need for and ability to create images).

Here are the constraints on zettel figure images:

* Must be a block (it's own line)
* Must immediately follow the title or video line 
* Only a single image is allowed
* No alternative "description" in the Markdown link
* Only raster images may be embedded
* Any and all raster images formats allowed
* Only JPEG, GIF, and PNG images
* Not to be linked to anything
* No larger than 2048 x 1080
* Name must be `figure-<width>x<height>.{jpg,gif,png}`

> 💡
> Since SVG images will likely gain wide support because of security
issues they present, they may still be added to a zettel directory and
mentioned in the references list. Do not attempt to link to them. Such
links are brittle and unsustainable. If and when your content moves
those links will no longer resolve. Instead say something speakable like
"20210813204720 (contains high resolution SVG)".

