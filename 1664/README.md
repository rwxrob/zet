# Always Create Aliases with Single Quotes

Although it is not immediately obviously why, creating aliases using
single quotes stops all of its variables from being replaced at that
moment. This means they will be evaluated and use the values for those
variables at the time the alias is called. Understand what would happen to
the following if defined with double quotes.

```sh
alias log='cd $(date +%Y%m%d)'
```
