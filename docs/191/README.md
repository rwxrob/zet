# Using USB as Git Repo in Windows WSL2

Make sure you mount the USB to a folder (instead of just a letter). And
make sure you install full Git on your Windows host computer and add
both the following to your path in your `$profile`:

```
$env:path = $env:path + ";c:\program files\git\bin;c:\program files\git\mingw64\bin"
```

* Assign a mount point folder path to a drive. \| Microsoft Docs  
  <https://docs.microsoft.com/en-us/windows-server/storage/disk-management/assign-a-mount-point-folder-path-to-a-drive>
* <https://stackoverflow.com/questions/58071729/problem-cloning-bare-repository-from-windows-10-git-server-to-windows-7-client>
