# Massive outlines in every Web page is an anti-pattern

Anyone using text-based browsing of a Web site that contains any sort of outline navigation on the side knows exactly how broken such outlines are. The problem, as usual, is that everyone has forgotten that the Web is first and foremost a text document distribution system. If even one of these developers even knew what `lynx` or `w3m` was they would never put these massive, broken outlines into *every fucking page*.

What makes it even more tragic is that they never needed to do that in the first place. It is ridiculously easy to pull down this information dynamically and cache it into the graphic browsers that actually benefit from it. Then that same JavaScript could use it for all kinds of cool navigation widgets. That would automatically make sure no text-based browser is burdened with what can be 20 pages of text to space through before getting to the actual Web page content that you care about.

It is definitely painful being someone who prefers the terminal for research for all the obvious benefits it provides. Here's yet another reason to keep the terminal faith alive, to *really* show the world that the terminal is, indeed, the fastest human-computer interface for those who take the minimal effort it takes so learn it.

For the rest of the GUI muggles? Well, unfortunately we have to live among them. But we don't have to like it.

Don't get mad, get busy.

I have a lot on my plate, mostly because so much of this makes me so angry because of the absolute unnecessary loss of efficiency. But I guess I just added another full-course meal to that plate: a lynx/w3m replacement that detects and discards anything that looks like one of these shitty navigation outlines.
