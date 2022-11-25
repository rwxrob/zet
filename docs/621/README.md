# Install Git in Windows PowerShell

You may have to enable scripts:

```powershell
Set-ExecutionPolicy RemoteSigned
```

Or if you are more paranoid:

```powershell
Set-ExecutionPolicy -Scope LocalMachine -ExecutionPolicy RemoteSigned -Force
```

All of the following fail as of this writing because there is no binary
created. I'm sticking with `git-scm` for everything.

* Install Git in PowerShell - MikeLizotte  
  <https://mikelizotte.ca/2021/09/24/install-git-in-powershell/>
* Git - Git in Powershell  
  <https://git-scm.com/book/ms/v2/Appendix-A%3A-Git-in-Other-Environments-Git-in-Powershell>
* Using Git with PowerShell on Windows 10  
  <https://www.develves.net/blogs/asd/articles/using-git-with-powershell-on-windows-10/>
