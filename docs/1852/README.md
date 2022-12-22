# How do you do unique identifiers?

https://github.com/rwxrob/uniq is the Bonzai command I use. I just added isosect based on a request. There are many ways to use uniqueness, use the best for you:

* isosec  - sortable unique second in GMT
* isosect - sortable unique second in GMT (with T)
* isonan  - sortable unique nanosecond in GMT
* hex     - pseudo-random bytes as hexadecimal
* second  - UNIX second since epoch
* uuid    - standard UUID v4 (RFC 4122)
* base32  - base32 20 byte unique identifier

