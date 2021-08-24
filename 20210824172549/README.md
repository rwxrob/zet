# TIL `ip -j` Outputs JSON Data

I've never been a fan of `ip`, until today. I hate that they invented
yet another syntax for the good 'ol `ifconfig` output. Then I read a
nice blog about UNIX philosophy in the 21st century with this example in
it:

```
ip -j addr show dev ens33
```

That's JSON output that it produces. Combine that with `jq` and, well,
I'll never use `ifconfig` again.

* [20210823020554](/20210823020554/) The (Actual) UNIX Philosophy
* [20210526203339](/20210526203339/) JSON Output Parsing with `jq` if You Can
* [Bringing the Unix Philosophy to the 21st Century \| Brazil\'s Blog](https://blog.kellybrazil.com/2019/11/26/bringing-the-unix-philosophy-to-the-21st-century/)

Tags

    #unix #json #jq #bash #scripting #linux #ip #ifconfig
