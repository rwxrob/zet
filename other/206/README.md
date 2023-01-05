# Why Doesn't Decimal Work with Float in python?

📺 <https://youtu.be/gfLe4fI5VX0>

```python
#!/usr/bin/env python3
from decimal import *
a=Decimal(1000000000000000000000000000000000000.0)
print(a)  # y is this value so different?
b=1000000000000000.0
print(a-b)
```

There are several problems with this related to the way Python handles
numbers. 

1. The biggest integer you can create is `2^64-1`
   (18446744073709551616).
2. `Decimal()` is a class constructor that takes a string
   counter-intuitively.
3. `Decimal` type is *not strictly* a number.

The Decimal type gets around the problem of dealing with very large
numbers that cannot be accurately represented by computers with a
maximum of `2^64-1` but when you use it, you have to use it for
everything.
