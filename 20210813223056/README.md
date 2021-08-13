# Q: Does bash do function 🏗 hoisting?

No. It cannot call a function until after it has been defined. Also
remember that `export -f ` is *not* hoisting. Python also does not do
function hoisting, and JavaScript does it *only* when using the
old-school `function` keyword.

Bash

```bash
#!/usr/bin/bash

# yes, hoisted 🏗
greet

greet() {
  echo hello
}

# NO, not hoisted
#greet
```

JavaScript

```js
#!/usr/bin/node

greet()

// hoisted!
function greet() {
  console.log("hello")
}

// NOT hoisted
//const greet = function() {console.log("hello")}

// NOT hoisted
//const greet = () => console.log("hello")

```

Other references:

* <http://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Functions>
