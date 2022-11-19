# Packages Don't Have Own State in Golang

Just a reminder that unlike other languages packages themselves have no
state and cannot be used as operands or arguments in the Go programming
language even though a "package variable" is one that is visible to the
entire package through the user of `var` declaration outside of any
function. The closest approximation would be to declare and assign a
package scope private variable and delegate package functions to it
resembling method calls on the package itself.
