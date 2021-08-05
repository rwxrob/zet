# Just Wrap at 72 Columns, Please

Say you just want to real a YAML file with a text block and come to find
out the person who wrote it had 90+ columns set for their wrapping, and
has decided to punish anyone fewer than 90 columns. It's at these times
that we realize the 72 column wrap (which has been the standard for
several decades and continues to be the standard for Go documentation)
remains a valuable default. 72 columns leaves the standard amount of
columns for line numbers and gutter in all text-based editors.

One modern reason, is for the sharing of code and content in videos such
as these so people can read the screen more appropriately. We can all
agree most video content uses text fonts that are woefully too small for
even the youngest eyes to read.

Another option is just to not wrap at all and let the terminal window
handle the wrapping for the user, no matter what the width. But
purposefully choosing to arbitrarily wrap at 90 doesn't make anyone
happy. Please, just consider it. 
