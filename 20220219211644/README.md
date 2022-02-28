# Windows OpenSSH Annoyances

> If the user belongs to the administrator group,
> `%programdata%/ssh/administrators_authorized_keys` is used instead of
> the one in the user home directory.

Remember, you cannot edit this file unless you are "admin", which
probably means you need to open notepad.exe as administrator and then
find the file.

It is unnecessarily complicated to start a "new" Windows terminal as
administrator. Notepad is actually easier. 

Also note that browsing with explorer.exe will not show 'c:\programdata'
since it is hidden by default so you have to type it into the file
path box.

The good news is that as soon as all of this is working you can use ssh
for *everything* including --- wait for it --- Ansible playbooks that
  apply to local desktop Windows configurations.

* OpenSSH Server configuration for Windows \| Microsoft Docs  
  <https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_server_configuration>

    #windows #openssh #linux #secops
