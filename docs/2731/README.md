# Open multiple source files at same time for completion

Realized after a lot of help from my streaming community that I was not getting the full benefit of completion without opening all the files with symbols in the same vim session. This is not even an LSP or NeoVim thing, just omnicomplete. 

For example, while factoring strings out of error in Go I had to open the file with all the string constants with long names to replace the strings in the errors code in a different file. When the constants file was closed I could not complete the names of those constants.

Note, however, that the files opened after the first will not have their content loaded into the buffers making them available for completion so make sure to open the files with the symbols to be used first and `:n` to the one for the edit.
