# Disable Accidental Terminal Suspends

You'll inevitably type Control-S on accident and find that your terminal freezes up even though everything else on your computer, including other terminals still works. This is because you have suspended (officially "stopped") the terminal output temporarily but it is buffering up everything you type and getting ready to print it when you resume it (with Control-Q). This is a left-over from the era of teletype machines that created the terminals (`tty`) that we have today. To disable this add `stty stop undef` to your `~/.bashrc` file.
