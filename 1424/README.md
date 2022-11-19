# Keep a Log in Git (Especially Contractors at Work)

This is the first time I've been a full-time contractor and the value of
having a log is not just high, it's mandatory. A large part of the
operations role (SRE if you insist) is to identify and raise
infrastructure issues, and then remediate them. Having a time-stamped,
irrefutable log of your discoveries and work not only helps you remember
what you discovered in a Markdown way that allows for code snippets and
such, but also eliminates drama when shit hits the fan. 

Such a record allows you to "boil the water" or report "the sky is
falling" and then record that you did without seeming ike an asshole.
You can just mention it through the appropriate channels and log it into
your GitHub private Zettelkasten log and move on. If no one does
anything about it, well, that's on them, not on you anymore. You brought
it up. You have a solid record of it. You can focus on the task at hand
(that they decide has a higher priority) and have your ass covered by
GitHub version control and time stamping. This is *far* more trustworthy
than just keeping some sort of log document around or (God forbid) Slack
messages and email. If others want to follow your work they can, but
they don't have to. They get fully indexed search capability of your
logs for free when you host them on GitHub Enterprise (sounded like an
advertisement).

The tough part is that you have to make sure to make entries that are
relevant and succinct. My simple `zet` multicall script symlinked as
`log` does the trick very well. In fact, I use `log` at work far more
than on my personal projects. It takes just a few seconds, but usually a
minute to make a log entry for a particular discovery. I've found that
the Zettelkasten repo approach is best because the files are all
consistent and there is no repositioning or anything to get to the right
location. This also saves people from unnecessarily scrolling after
finding search hit results.
