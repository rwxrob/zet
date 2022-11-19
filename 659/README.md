# Rethinking Zet as Part of KEG Node

All the linking I have build into `zet` repo currently assumes you are
always the highest thing so the links are relative and directly the
root. This was because of GitHub and I've decided to change it. But it
means no more depending on GitHub for reader consumption (although
searching will still work). The `rsync` protocol will be the standard
for KEG exchange and backups.

GitHub is totally fucking brain dead when is comes to linking between
README.md files in subdirectories. But, I suppose that is GitHub's fault
and I shouldn't cater to it. Besides, GitHub stops becoming a reasonable
place to store zettels as soon as you hit 1000 and it just decides to
not show them anymore. And, after all, Git is the wrong technology for
KEG in the first place. You really don't want all the back versions of
everything. You only want the latest and if you want a backup you make a
fucking copy of the file and save that. In this sense, knowledge
management is distinctly different than source code management.
