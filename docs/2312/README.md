# Joining video files with `ffmpeg`

Using `ffmpeg` from the command line is by far the most efficient way to join common video formats. Note that this method does not re-encode the video (which would cause unavoidable loss of resolution and add artifacts).

```sh
ffmpeg  -loglevel info -f concat -safe 0  -i files.ffmpeg -c copy   newfile.mkv
```

Then, make sure to have the full path to the files in the `files.ffmpeg` text file.


```ffmpeg
file '/home/rwxrob/somefile1.mkv'
file '/home/rwxrob/somefile2.mkv'
file '/home/rwxrob/somefile3.mkv'
```

Eventually, I need to put this into a script.

