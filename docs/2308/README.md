# ChatGPT fails again, another reason never to trust it

The following automatically generated Go code by ChatGPT uses a library that has been deprecated for more than three years. *NEVER* trust code generated by any AI. *Always* confirm it with someone who actually knows how to code in that language and has some amount of experience. In fact, when directly asked if `ioutils` was deprecated ChatGPT gave this very incorrect response:

> There is no record of the "ioutils" package being deprecated in the official Go repository. The "ioutils" package is still maintained and used in Go programming.

Keep in mind that this is from ChatGPT data that is supposed to cover 2021, which is the year that it was deprecated. Some members of Twitch community confirmed that other AIs got it right noting the deprecation date in February of 2021.

The point is, just don't trust these AIs all by themselves. They are meant to nudge you in the right direction and job your memory, not replace your brain.

## Full (incorrect) ChatGPT response

Here's an example of Go code that can help you achieve that:
```go
package main

import (
        "fmt"
        "io/ioutil"
        "log"
        "os"
        "path/filepath"
)

func main() {
        dirname := "/path/to/directory" // Replace with your directory path

        files, err := ioutil.ReadDir(dirname)
        if err != nil {
                log.Fatal(err)
        }

        for _, file := range files {
                if !file.IsDir() {
                        // If the file is not a directory, print its name and exit loop
                        fmt.Println(file.Name())
                        break
                }
        }

        fmt.Println("Done.")
}
```
Note: Replace "/path/to/directory" with the actual directory path you want to search for the file in.

This code uses the `ioutil.ReadDir()` function to read the contents of the directory specified by `dirname`. It then iterates over each file in the directory using a `for` loop. For each file, it checks if it is not a directory using the `IsDir()` method of the `os.FileInfo` struct. If a file that is not a directory is found, it prints the name of the file and exits the loop. Finally, it prints "Done." as a confirmation that the search is complete.
╔