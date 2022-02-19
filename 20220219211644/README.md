# Windows OpenSSH Annoyances

If the user belongs to the administrator group,
`%programdata%/ssh/administrators_authorized_keys` is used instead of
the one in the user home directory.

It is unnecessarily complicated to start a "new" Windows terminal as
administrator. Notepad is actually easier. 

Remember, you cannot edit this file unless you are "admin", which
probably means you need to open notepad.exe as administrator and then
find the file.

Also note that browsing with explorer.exe will not show 'c:\programdata'
since it is hidden by default.

* OpenSSH Server configuration for Windows \| Microsoft Docs  
  <https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_server_configuration>
