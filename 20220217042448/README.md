# Apparently `strings.Fields()` Exists in Go

I cannot believe I never saw this before. If you are using
`strings.Split(foo," ")` you likely have substantial bugs. Use
`strings.Fields()` instead.

    #golang #strings #tips
