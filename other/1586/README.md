# Use `gsudo` Like `sudo` for Windows

TIL there's a thing called `gsudo` that perfectly behaves like `sudo` on
Windows. I believe it even can be used under WSL2 to replace the actual
`sudo` but I've not found that. I went ahead and wrote the following
PowerShell (as recommended) to actually install it from a PowerShell
command line.

```powershell
PowerShell -Command "Set-ExecutionPolicy RemoteSigned -scope Process;
iwr -useb
https://raw.githubusercontent.com/gerardog/gsudo/installgsudo.ps1 | iex"
```

> ⚠️
> The code looked clean to me when I looked through it, but do your own
> validation before trusting that install to your own computer.

After you do this you'll be able to use `gsudo` anywhere you normally would have to run another terminal shell just to get admin privileges.

```
PS C:\Users\rwxrob> gsudo ls
```

You'll note that the system will pop up a window saying you want to do
something as administrator.

I can't believe I am saying this, but I could get okay with working from the Windows shell if I had to (and only if I had to). I like having a decent understanding of how PowerShell users would start monolith commands developed in Go. I'm finding that a substantial number of enterprise Cloud-Native engineers and developers are actually using Windows shells for things. I think it's disgusting, but it is the reality for some. Might as well learn it. I don't want to force people to use Linux when Go works on anything.

Related:

* GitHub - gerardog/gsudo: A Sudo for Windows  
  <https://github.com/gerardog/gsudo>

Tags:

    #til #sudo #windows #tips #secops
