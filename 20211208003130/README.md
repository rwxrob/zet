# Use `curl -o ... -w ...` for Effective Return Code

Sometimes you want to get the HTTP response code before you decide
to do something with what you downloaded using `curl` ---
especially if the response code is anything but 200 (meaning you
probably didn't download what you wanted. By separating the output
with `-o` you can use `-w %{response_code}` to print the numeric code to
standard out and exam that easily in a condition.  

```
curl -sSL 'https://raw.githubusercontent.com/rwxrob/k8sapp-nfd/ma│ in/check' -o /tmp/foo -w '%{response_code}' 
```

Related:

* `man curl`

Tags:

    #curl #tips #https #hacking #devops
