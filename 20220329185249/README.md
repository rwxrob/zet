# More Evidence Go is a Favorite for Hackers

In 2021 there was a massive increase in malware written in Go. Here are
just a few:

* **ElectoRAT** - info stealing that went a year without detection
* **RobbinHood** - ransomware that crippled hospitals
* **Zebrocy** - MS Word phish
* **Veil** - metasploit hidden by compiling into Go
* **GoBot2** - botnet using Go's massive concurrency support
* **HERCULES** - create payloads that bypass antivirus software

> "Additionally, the most prevalent malware groupings included >
> Pentesting, Remote Access Trojans (RATs), and Backdoors."

Go is absolutely ideal for all of this because of how extensive the
standard library is, how modular it is (Bonzai), and how good it is at
hiding itself.

People are taking old C code hacks, wrapping them in Go, and redeploying
(which just shows how fucking stupid most security software actually
is). And now we have `garble` to make things even more interesting.
There is absolutely no doubt in my mind --- especially after creating
Bonzai for monoliths of composable command trees and using all of the
standard library stuff for encryption --- that Go will be the dominate
hacker/security language within five years.

* <https://github.com/burrowers/garble>

* Golang based Malware: Things to know \| Brainfuel Blog  
  <https://www.brainfuel.io/blog/golang-based-malware-things-to-know/>

* Financial Motivation Drives Golang Malware Adoption \| CrowdStrike  
  <https://www.crowdstrike.com/blog/financial-motivation-drives-golang-malware-adoption/>

* What You Need To Know About Golang-Based Malware  
  <https://www.makeuseof.com/what-you-need-to-know-about-golang-based-malware/>

    #golang #opsec #hackers #malware
