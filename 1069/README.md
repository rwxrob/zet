# Use Package `var` for Function Aliases

In most languages you can create a function with an identical name to
another in other namespace with just an assignment. Go is no different,
but unfortunately it has to be a variable and not a constant.
Technically, this would allow other developers using your package to
change the function being used, which might actually be desirable in
some cases. The only hit is that variable assignment is a runtime
operation while creating a function requires a delegated function call.
I don't know for sure, but I'm pretty sure the variable assignment is
much faster.

    #golang #coding #tips
