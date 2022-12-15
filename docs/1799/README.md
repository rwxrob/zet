# ⚡ Share a folder between Windows and Linux

It's always easier to create a samba share on the Linux machine and add that "network drive" from the Windows machine. The reverse can be quite painful with all the craziness with username and password setups now that the cloud is the default Windows login method.

First, find out which workgroup your Windows machine is in. It should be under **Computer Name, Domain and Workgroup Settings**. Usually, it's just "WORKGROUP". You can get there fastest by just tapping the command/windows key and typing "workgroup".

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

Then let's test it out with `smbclient` before trying anything else to make sure the mount, domain, and user are setup correctly.

```sh
$ smbclient //198.19.1.14/Pictures
Password for [WORKGROUP\rwxrob]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Thu Dec 15 02:14:49 2022
  ..                                  D        0  Thu Dec 15 02:15:04 2022
  README.md                           N       43  Thu Dec 15 02:14:49 2022

                307672240 blocks of size 1024. 244110992 blocks available
smb: \>
```

Looks good. Now to try mounting it from the remote/host Windows 10 machine. In my case, this is the same physical machine since I run `anton` inside a VMware virtual machine hosted on Windows 10 and connected via ssh on the same shared network.

Now we have to add a network mount in Windows 10. Open the **File Explorer** and find **This PC** icon in the left pane. Right click it and **Add Network Location** then click **Next** and **Choose a custom network location** and **Next**. Then, type in the exact same location path that we tried with `smbclient` but with the *slashes in the opposite direction* and without the username (`rwxrob@` for which it will prompt).

🤚 Did you make sure your slashes were backward and not forward? (That's the biggest gotcha I've encountered at this step.)

You should be able to click **Browse** and see that everything worked.

Accept the default for **Type a name for this network location** and click **Next**.
nd then **Finish**. You should now see your new directory mount any time you open the file explorer.

In my case, I'm going to change all my screenshots to save into the directory share by default so that I can easily add them to my zettelkasten keg site from the terminal even though I'm making the screenshots from Windows.

* How to Setup CIFS on Windows 10 to Share a Folder on the Network - Contrado Digital  
  <https://www.contradodigital.com/2019/09/08/how-to-setup-cifs-on-windows-10-to-share-a-folder-on-the-network/>
* TechRepublic on Flipboard  
  <https://www.techrepublic.com/article/how-to-create-a-samba-share-on-ubuntu-server-20-04/>
* How to Connect to Linux Samba Shares from Windows 10  
  <https://www.techrepublic.com/article/how-to-connect-to-linux-samba-shares-from-windows-10/>
