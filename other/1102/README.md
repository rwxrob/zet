# Adding to PATH in PowerShell

It's a pain in the ass, but you'll need to add the following to your
`C:\Users\rob\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`
file for things like `git` and the like that don't put stuff in expected
places:

```powershell
$env:path = $env:path + ";c:\program files\git\bin"
```

* PowerShell Profiles and Add-Path \| Splunk  
  <https://www.splunk.com/en_us/blog/tips-and-tricks/powershell-profiles-and-add-path.html>
