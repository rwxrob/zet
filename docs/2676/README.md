# Mac is bsd therefore no `date -d` (sigh)

```bash
#!/bin/bash

if [[ "$OSTYPE" =~ ^(darwin|bsd) ]]; then
	if [[ -z "$1" ]]; then
		date "+%A, %B %e, %Y, %l:%M:%S%p %Z"
	else
		date -v"$*" "+%A, %B %e, %Y, %l:%M:%S%p %Z" 
	fi
	exit
fi

if [[ -z "$1" ]]; then
	date "+%A, %B %e, %Y, %l:%M:%S%p %Z"
else
	date "+%A, %B %e, %Y, %l:%M:%S%p %Z" -d "$*"
fi
```

