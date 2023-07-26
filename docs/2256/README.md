# Document Go structs within the definition block, here's why

> gpt should i put the comments for a golang struct inside of the struct definition block or in a precending comment for the entire struct itself

> "It is recommended to put the comments for a Golang struct inside of the struct definition block, as it helps to document the purpose and usage of each field within the struct. This way, the comments are directly associated with the specific fields they describe, making it easier for other developers to understand the code when they read it. Placing comments inside the struct definition block also aligns with the Go standard convention for documenting code."

This has always annoyed me, until today when I realized there is a *very* good reason to document these struct fields in this way (despite how annoying it is to see all of the struct fields together). That reason is `gd` when using the `vim` editor. It jumps to the source. Doing this with the documentation for that field in the comment for the entire struct as some sort of pseudo-bullet point makes it that much harder to realize just what the field is for. You want to see that comment on the same screen way more than you want to see all of the fields combined for a given struct.
