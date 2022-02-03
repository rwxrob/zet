# Make Sure to Use SHA-512 for Passwords

```
mkpasswd -s -m sha512crypt <<< mypassword
```

The type of password algorithm is stored in `/etc/pam.d/passwd`.

* Is sha256 deprecated?  
  <https://ameswanda.ddns.us/is-sha256-deprecated>
* Changes/yescrypt as default hashing method for shadow  
  <https://fedoraproject.org/wiki/Changes/yescrypt_as_default_hashing_method_for_shadow>
* Security/Features - Ubuntu Wiki  
  <https://wiki.ubuntu.com/Security/Features>

    #security #passwords #secops #devops #linux
