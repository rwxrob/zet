# Disable Swap on Linux

Need to disable it on the current running system and disable the swap
partition for the next book in `/etc/fstab`.

```
sudo swapoff -a
sudo sed -i '/ swap / s/^/#/' /etc/fstab
```
