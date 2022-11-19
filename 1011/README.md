# Origin of `/var/lock` Locking Standards

So it looks like `/var/lock` has been a thing since 2004 and I just
missed it. 

 "Filesystem Hiearchy Standard" /var/lock has been specified at least
 since 2004. Here is the current (2015) spec. It even includes how the
 PID should be stored with a newline. It is different how I would have
 expected it =>
 <https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.html#varlockLockFiles>
 However, I have also lock files in my home directory and in
 `$XDG_RUNTIME_DIR`.
