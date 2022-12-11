# ⚡ Secure shell (ssh) client in 80 lines of Go code

📺 <https://youtu.be/6mP20OGQAlw>

Sometimes you need a tool or service to run a command on a remote system and capture its output safely. Secure shell has long been the tool for making such remote connections. Thankfully, Go comes with the standard `crypto/ssh` package which has full support for creating both ssh clients and servers. But with all that power it can be hard to just do the regular easy stuff, like just run a command and get its output. This process can be simplified by making some sensible assumptions about default settings. Here's how to do that in Go.

One great advantage of this approach is that there is absolutely no requirement to install any ssh packages on the host system at all. The Go `crypto/ssh` library covers all the bases enabling things like `FROM SCRATCH` containers that encapsulate a single binary that includes a light-weight, fully functional ssh client.

1. Get the user and target host IP and port
1. Create an SSH client and dial a TCP connection
1. Create a Session and set parameters and stdin (if we have it)
1. Run the Session to execute the command remotely
1. Buffer the stdout, stderr into strings
1. Return the stdout, stderr, and errors (if any)

Bonus: timeout after a reasonable about of time.

* <https://github.com/rwxrob/ssh>
