# Resolving Problems with Badge "Requirements"

Although the Scout Merit Badge system has resolved several problems with
the organization of consumable objectives, I'm facing my gripe I have
always had with the system: its rigidity.

Being able to refer to a requirement by number (ex: 1b) is sometimes an
advantage but usually it is a problem for the following reasons:

**The number infers order** where there is none. 

**Order changes** disrupt the number system and anyone depending on the
numbering system in chart completion summaries, etc.

**No versioning** makes it impossible to know if you have the right list
of requirements. The program refers to versions by specific date of
revision. Ironically, this is something that would benefit from a
specific semver versioning system.

**Parent requirements groupings are vague** and usually read "Do three
of the following" even though many of the listed sub-items make no sense
when grouped together in any way. This seems to allow flexibility in the
requirement by adding and removing options over time without impacting
the ordering, although some have been replaced in the past.

In a nutshell, the Merit Badge outlines are a crusty, broken vestige of
bad organizations decisions made in 1910 before software was a
house-hold name. Even young people playing games know what a "version"
is these days. It's time that any learning content organization system
take on the properties of successfully managed software, but how?

**Drop numeric references entirely** since they are far too rigid. Even
when they seem to be valuable (in progress charts) they fail to prevent
those using such tools from looking them up anyway. Technology allows
far greater flexibility in summary and display applications.

**Use language taken from a job description** for top level requirement
groups. For example, "Demonstrate effective use of the filter command"
might be the top-level with a bunch of sub-level options that are
concrete examples.

**Remove "one of ..." language** since there is no hard and fast measure
of these requirements going on. These are all for self-assessment (or
assisted self-assessment). Consider giving each a weight which combines
into a weight for the entire grouping providing some metric for that
parent requirement. Adding addition items to that grouping simply
provide further opportunity to go deeper and increase one's depth or
weight score for that grouping. Weights can be changed over time without
impacting tracking (like changing the Dota2 meta).

**Provide time estimates to grouped line items** so that they can be
folded up into a suggested time required to complete a particular badge.
This will provide a real-time estimate of the scope of the badge while
developing it.

**Give badges semantic versions** so people know when there has been a
breaking change (that would cause getting it again) versus just updates
or errata.
