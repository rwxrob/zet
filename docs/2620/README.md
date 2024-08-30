# How to adduser or useradd on a Mac as admin

```sh
sudo dscl . -create /Users/USERNAME_HERE
sudo dscl . -append /Groups/admin GroupMembership USERNAME_HERE
```

* terminal - How to add a user from the command line in macOS? - Ask Different  
  <https://apple.stackexchange.com/questions/286749/how-to-add-a-user-from-the-command-line-in-macos>
