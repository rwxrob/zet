# Go Regexp has Unicode Classes!

I'm so happy! Go supports the `\p{L|Nd}` style of Unicode classes in
regular expressions. All those people using `\w` are DOING IT WRONG!
Just ask anyone who doesn't speak a language with an alphabet in the
ASCII character set. Thankfully, this means that my `scan.R.Match()`
method doesn't have to be supplemented with one that looks for Unicode.
My god. I. Am. Happy.

* UTS \#18: Unicode Regular Expressions  
  https://www.unicode.org/reports/tr18/

    #golang #coding #tips #regexp
