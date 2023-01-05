# Support for backtick (`pre`) in BonzaiMark

Now that the conventional way to maintain documentation for **Bonzai** **stateful command trees** is through the use of Go's amazing `embed` package full support for backticks can be added. Before, this wasn't possible because the documentation was inline within the main `cmd.go` source. But now, the entire file is loaded into a string making it *very* easy, much easier than the `{{pre "fmt"}}` template-heavy approach.
