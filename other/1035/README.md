# Flat-Files are Fine

People love to shit on the idea of using flat-files (plain text files)
for things like indexing, but it's *them* that are full of shit. Flat
files are often the *best* approach to indexing knowledge because they
can be consumed by anything — no really, *anything*. You can’t say that
of an SQLite DB files and the like, hell, you can't even say that about
XML or CSV files.

Flat files also do not require any cognitive overhead or special skills
to use and maintain. Anyone who can read and write can make sense of
them and use them immediately. Those with minimal scripting skills can
iterate over every line in their own way, even import them into
spreadsheets or their favorite database engine. 

Flat files fulfill the well-established "progressive design" principle.
Use the least amount of technology possible and progressively add
support for more technology as it is detected, but never *assume* you
have it. Assuming everyone has SQLite, for example, is an example of
violating that principle. When it comes to universal, sustainable
knowledge storage, sharing, and management we most definitely want the
least possible technology requirements.

