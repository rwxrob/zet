# Use `ssh-keygen` to create generic key pairs without user info

Sometimes a generic SSH key pair is needed for testing or other purposes where using a user's specific key is less desirable. In such cases, simply overwrite the comment and force the key pair to be written someplace else. This key can then be used with `ssh -i <path>` just like any other. This has the advantage of not giving up user-specific information in examples and such.

```
ssh-keygen -C mycomment -f /tmp/somekey -t ed25519
```

```out
Generating public/private ed25519 key pair.
ssh_askpass: exec(/usr/bin/ssh-askpass): No such file or directory
ssh_askpass: exec(/usr/bin/ssh-askpass): No such file or directory
Your identification has been saved in /tmp/somekey
Your public key has been saved in /tmp/somekey.pub
The key fingerprint is:
SHA256:ARai5uV1hy1PVQuS1N31XtCAf6Ia7v5cNhOwmb3ORAc mycomment
The key's randomart image is:
+--[ED25519 256]--+
|    . +. .ooo+++o|
|   . o . o.oo..o+|
|  o . . = + ..E o|
| o o . . *   *ooo|
|  . .   S . +.+oo|
|          . .. + |
|         . o  B  |
|          o. * o |
|         oo.o o  |
+----[SHA256]-----+

```

Now when this is added to `~/.ssh/authorized_keys` it will have generic comment information (as opposed to your own).

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIHDfdSyeUQBvYvV2aeseg13SMLql0chedsl80kd9BKgc mycomment
```

