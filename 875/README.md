# Files < 60 Bytes Never Stored to Disk

Sporidium from Twitch community uncovered an interesting factoid. With
`ext3` Linux filesystem if a file's contents is less than 60 bytes it is
saved in the inode itself and not actually to disk. It looks like it
saves it to disk for persistence, but once that directory is opened in
any capacity the content of the file is loaded with the inode. This
means that a directory with small text values in it could actually be
faster to open and read/write than the equivalent data in a structured
data file (YAML, JSON, etc.).

    #linux #fs #inodes
