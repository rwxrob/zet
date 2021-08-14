# Only Perl and C Let You Change Running Process Name

I used to love changing the name of a running Perl daemon (service) to
show what it was processing --- especially if more than one forked
process was working on it. Each child could update what appears in `ps
-ef` output to show the current state and file it was working on. That
is *hugely* valuable in operations and systems programming. Here's what
the code looks like in Perl.

```perl
#!/usr/bin/perl

$count=1;
while (true) {
  $0="foo: $count";
  sleep 1;
  $count++;
}
```

However, such is not possible in Bash, despite the description of
`$BASH_ARGV0` which suggests this is possible. Perhaps `$0` is changed,
but not the value of `/proc/pid/cmdline`, which is what appears in the `ps
-ef` output.

We found some Go code to do similar things, but it requires CGO to be
on.

References:

* <https://github.com/erikdubbelboer/gspt>

    #unix #linux #sre #devops #tips #coding #perl #golang #c
