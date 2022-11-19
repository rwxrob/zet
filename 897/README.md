# Another Reason to Use Plain Vim Line Numbers

I've never been a fan of relative line numbered in Vim. I get why people
like it. I just don't happen to agree with that method of navigation and
matching. Instead I use `/` for just about everything. But recently I
learned of another very solid reason to never use it at all: GitHub URL
links.

GitHub supports adding `#L10-L20` notation to link and highlight a
specific section of code. I cannot overstate how important this is. By
making extensive use of this URL approach education and other
documentation becomes a breeze. Besides, if you are maintaining code in
markdown someplace and not directly linking to working examples in
GitHub you're fucking doing it wrong. By promoting use of GitHub for
*everything* including references to specific code in your documentation
you are directly promoting use of one of the most important professional
tools anyone can ever learn. Your code is runnable. Your readers can
clone the code locally with a single command and mess with it. And your
documentation remains always up to date if you decide to change the code
examples. If you are paranoid, you can just use the single (`#L10`) URL
method since the width might change.

What is even crazier is that languages like Go have internal knowledge
of where functions and types appear so that tools can easily be created
to *automatically* create those links for you based on the name of the
thing you want to document. Humm, I feel yet another Vim filter coming
on.

    #vim #golang #github #git #education #edtech #writing
