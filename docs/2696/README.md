# LOG20240914085229: Saturday, September 14, 2024,  8:52:29AM EDT

I think rather than continue to make shell scripts or even independent Go CLI commands that I need to create a standard for composable Cobra commands and create a tool for initializing Cobra compatible stuff. I'd name my command `cobra-cli` just because the official one is, um, not good.

> 🤷 There is that better than calling it absolute shit? "Not if you call it out, Rob!" Hey, I'm at least sort of trying.)

I could keep the legacy behavior, or not. It's really horrible. I mean, how short-sighted can you be to not see the benefit of subdirectories to contain nested subcommand trees?
