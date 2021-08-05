# Know How Bash Regex and Patterns Differ

Say you want to match a regular expression and get a capture a run of characters
from it, but then you also want to replace characters in that same line.
To do this entirely in Bash requires use of *both* a regular expression
and a parameter expansion pattern match.

Study the following script to understand what is going on. 

* Can you spot the regular expression? 
* What type of regular expression is it? Which engine?
* Can you spot the pattern match parameter expansion?

<https://raw.githubusercontent.com/rwxrob/dot/main/scripts/toduck>
