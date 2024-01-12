# Slow sudo from missing /etc/hosts hostname

Today I learned that the `sudo` command does a DNS lookup and that if you do not have your current host name in the `/etc/hosts` file it can take a very long time to exhaust all the DNS options. All I did was add my current host name from my CLI prompt into my `/etc/hosts` file for `127.0.0.1` and everything started working again.

