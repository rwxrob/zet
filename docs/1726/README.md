# Git fails to recognize `/usr/bin/pager`

Yeah, just when I thought surely I was doing something wrong I discovered that the all-powerful, famous `git` program is totally broken on all major UNIX systems. People just don't notice, until they try to do similar shit and actually read about the established conventions instead of doing what the Git team has apparently done: just make `less` the default.

Not only that, but this code from `pager.c` proves they are just blowing away the `LESS` and `LC` environment variables with their own, disrespecting anything the user might have added there:

```c
   (void) term_columns();
   setenv("GIT_PAGER_IN_USE", "true", 1);
   /* spawn the pager */
   pager_argv[0] = pager;
   pager_process.use_shell = 1;
   pager_process.argv = pager_argv;
   pager_process.in = -1;
   if (!getenv("LESS") || !getenv("LV")) {
     static const char *env[3];
     int i = 0;
     if (!getenv("LESS"))
       env[i++] = "LESS=FRX";
     if (!getenv("LV"))
       env[i++] = "LV=-c";
     env[i] = NULL;
     pager_process.env = env;
   }
```
