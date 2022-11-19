# Golang Better Than Bash, Perl, Python for Tools

I was about to do some expanding on my `yt` Bash script to work with the
YouTube API when I realized something: Go is better than Bash, Perl,
Python, Ruby, and NodeJS for utilities and tools, frankly than most thing
longer than 200 lines of code because it is easier to manage the source,
and share the binaries.

Let's say a Mac or Arch users wants my `pomo` timer but it was only
written in Bash (which would be easy enough). That forces them to
install Bash to just use it causing twice the effort. If I put the
binary releases in my Git repo along with the source --- and include
checksums of everything for validation against man-in-the-middle attacks
even though most people don't really care --- then all anyone has to do
is `curl` or `wget` the file and validate it, perhaps even in the same
command. There are *zero* dependencies on anything else.

It is true that it takes longer to write such tools in Go, but it is
worth it in the long run. Another obvious benefit is that much of the
code will take the form of library packages that themselves can be
reused elsewhere, and if I continue to use the `cmdbox-pomo` approach
people can even combine multiple tools into a single composite.

It was good to have this reminder. No wonder *all* cloud-native tooling
and operating systems are written in Go (and C for kernel).
