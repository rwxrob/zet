# Enterprise laptop/workstation gatekeeping

People who have filled their brains with unrealistic assumptions by watching too many YouTube Linux videos (mostly from people who *don't have jobs working with Linux*) always roll their eyes when I tell them that they probably won't have the control of the computer they are given to do their work on for a big corporation.

"What?! You mean I cannot run Linux on the desktop and install it myself? But *[popular-clueless- youtuber]* told me I am free to do whatever I want!"

The answer is NO FUCKING WAY! Make sure you ask if you can use Linux desktop in your job interview, because it definitely is *not* the norm. Often the choice is between gainful employment and having Linux on your work computer. They are mutually exclusive.

Here's one example that I hit recently.

The level of absolute paranoia that has permeated enterprise IT has reached entirely new levels. After creating a binary for use to login to Kubernetes our company won't even allow the binaries to be released on our internal GitHub release page because they are flagged by the Gatekeeper policy of the new Macs that are entirely centrally managed. Even people who have admin on their Macs have to download the corporate app store, run the `Allow Gatekeeper Bypass` *from the command line* and then they *must* double-click on the binary in order to trigger it being picked up. One step *must* be from the command line, the other *must* be by double-clicking a fucking command-line command that has no graphic use at all.

The levels of complete brain-dead flat-lining that are reaching these monstrously huge enterprises is absolutely astounding. They are getting dumber and dumber. (I won't even get into how they are forcing PAM to be replace by an OAuth2 web flow.)
