# Check length in Go for empty strings, it's fastest

I read this someplace else before (cannot remember where) but ChatGPT has the reminder.

## ChatGPT response

In Go, it is generally faster to check the length of a string rather than comparing it to an empty string. This is because checking the length is a constant-time operation, whereas comparing the content of the string requires iterating over each character.

For example, consider the following code snippets:

```go
func checkLength(s string) bool {
    return len(s) == 0
}

func checkContent(s string) bool {
    return s == ""
}
```

In the `checkLength` function, the length of the string is directly compared to zero, which is a very fast operation. On the other hand, the `checkContent` function compares the content of the string to an empty string, which requires iterating over each character in the string.

So, if performance is a concern, it is recommended to use the `checkLength` approach when checking for an empty string in Go.

