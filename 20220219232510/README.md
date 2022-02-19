# Change Default OpenSSH Shell on Windows

Personally, I keep mine as PowerShell since I can do things remotely
with `ssh` commands that do not work with Git Bash, such as opening the
local graphic web browser or playing video clips.

To change it to PowerShell:

```posh
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -PropertyType String -Force
```

To change it to Git Bash:

```posh
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\program files\git\bin\bash.exe" -PropertyType String -Force
```

    #openssh #shell #windows #tips
