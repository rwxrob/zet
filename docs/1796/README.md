# Share a folder between Windows and Linux

It's usually easier to create a samba share on the Linux machine and add that "network" from the Windows machine. The reverse can be quite painful with all the craziness with username and password setups now that the cloud is the default Windows login method.

First find out which workgroup your Windows machine is in. It should be under **Computer Name, Domain and Workgroup Settings**. Usually, it's just "WORKGROUP". You can get there fastest by just tapping the command/windows key and typing "workgroup".

Then we install `samba` in Linux.

```sh
$ sudo apt install samba
```

Then we need to edit the `smb.conf` file.

```sh
$ sudo vi /etc/samba/smb.conf
```

The line with `workgroup` may already be what you want.

```
   workgroup = WORKGROUP
```

Add a "shareable" entry near the bottom. Since there's already a group setup for each individual user I just used that.

```ini
[Pictures]
path = /home/rwxrob/Pictures
valid users = @rwxrob
browsable = yes
writable = yes
read only = no
```

Restart the `smbd` service.

```sh
$ sudo systemctl restart smbd
```

Samba requires users *in addition* to the regular system users. So let's add that now. I'm going to use the same name.

```sh
$ sudo smbpasswd -a rwxrob
New SMB password:
Retype new SMB password:
Added user rwxrob.
```

Now we have to enable the user.

```sh
$ sudo smbpasswd -e rwxrob
Enabled user rwxrob.
```

Here's how it might work if you want to try in reverse (share from Windows, mount in Linux):

```sh
sudo mount.cifs //198.19.1.10/Pictures /home/rwxrob/Pictures -o=rob@rwx.gg
```

* How to Setup CIFS on Windows 10 to Share a Folder on the Network - Contrado Digital  
  <https://www.contradodigital.com/2019/09/08/how-to-setup-cifs-on-windows-10-to-share-a-folder-on-the-network/>
* TechRepublic on Flipboard  
  <https://www.techrepublic.com/article/how-to-create-a-samba-share-on-ubuntu-server-20-04/>
