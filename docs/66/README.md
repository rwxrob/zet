# Run SSH Server on Windows

Since you cannot mount a USB into WSL2 I thought I'd get an SSH server
running on it and just use the ssh form of Git URLs to access the
private repo on it.

> lbgdn: Ok, the trick is to put the public key in
> `%PROGRAMDATA%\ssh\administrators_authorized_keys` and change security
> on it to only SYSTEM and Administrators full access. 

You might have to disable inherited permissions on the file in order to
remove the "Authenticated User" permission, which you can to in the GUI
or with the following commands:

```powershell
icacls C:\ProgramData\ssh\administrators_authorized_keys /inheritance:d
icacls C:\ProgramData\ssh\administrators_authorized_keys /remove "NT AUTHORITY\Authenticated Users"
```

I also forgot to set the default shell to PowerShell (which is covered
in the documentation, but here it is):

```powershell
New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" -PropertyType String -Force
```

I thought about making my default shell bash even on Windows, but that
is probably a bad idea given all the PS commands that I generally need
to run.

* OpenSSH Server configuration for Windows \| Microsoft Docs  
  <https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_server_configuration>
* Key-based Authentication for OpenSSH on Windows - Concurrency  
  <https://www.concurrency.com/blog/may-2019/key-based-authentication-for-openssh-on-windows>
