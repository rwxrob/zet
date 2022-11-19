# ImageMagick `identify` from Command Line FTW!

I cannot say enough about how amazing ImageMagick (`identify`) is for
dealing with images from bash and the command line. Have a look at this
example of converting a screenshot into a uniquely identified image file
name with the dimensions included and the time the file was created:

```bash
_figure_name() {
  _checkdep identify 
  identify -format "F$(date -u +%Y%m%d%H%M%S -r "$1")-%G.%e" "$1"
}
```

```
'Screenshot from 2021-08-31 13-14-01.png'
  -> F20210831170235-673x402.png
```

That's it. A thing of UNIX beauty.

    #images #cli #linux #bash #scripting #tips #raster
