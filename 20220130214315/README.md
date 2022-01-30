# Generating a GPG Key without Passphrase for GitHub

```
sudo apt install rng-tools
sudo rngd -r /dev/urandom
cat /proc/sys/kernel/random/entropy_avail
gpg --batch --passphrase '' --quick-gen-key 'Rob Muhlestein (rwxrob.tv) <rob@rwx.gg>' default default
```

* Generate GPG key without passphrase \| by Shawn Grover \| Medium  
  <https://shawngrover.medium.com/generate-gpg-key-without-passphrase-6dec71caecf8>
* Generate Enough \'Entropy\' For GPG Key Generation Process  
  <https://ostechnix.com/how-to-generate-enough-entropy-for-gpg-key-generation-process/>
