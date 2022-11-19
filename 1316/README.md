# Multi-Language Support Dilemmas

There are so many languages out there to support that trying to support
them all in a single program seems, well, foolish. First of all the
binary would be bloated unnecessarily, second there is still a lot of
disagreement on the best way to "internationalize" an application. 

I'm hitting this with CmdBox. I think I am overly abstracting it.
Besides, the package are already so modular that if someone wanted to
support multiple languages they could just by adding to the name:

`cmdbox-help`
`cmdbox-help-sp`

And people could then add composites for their targeted languages
without bloating them. There's nothing stopping them from putting the
core code into a common library that both the cmdbox command modules
call on. I feel like that is a better approach.

