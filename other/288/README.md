# Valid Hashtag Characters (in PEGN)

```regex
(^|\s)([#＃][\w\u05be\u05f3\u05f4]*[\p{L}_]+[\w\u05be\u05f3\u05f4]*)
```

＃

```pegn
Tag <-- '#'
```

* must begin with octothorp (`#`)
* numbers or letters
* underscore sparingly
* no dashes/hyphens
* no spaces
* don't start with numbers
* don't make entirely numbers

* What Characters Can A Hashtag Include?  
  https://www.hashtags.org/platforms/twitter/what-characters-can-a-hashtag-include/
* Twitter Hashtags  
  https://bloggingwizard.com/complete-guide-to-twitter-hashtags/
* regex - Which characters are allowed in hashtags - Stack Overflow  
  https://stackoverflow.com/questions/36895543/which-characters-are-allowed-in-hashtags
