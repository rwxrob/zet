# Having Windows to Test Go Installs is Heaven

There's no purer test of reality than pushing a command to GitHub and
then being able to `ssh` into the Windows side of my desktop system and
attempting to pull it down. By doing this I've caught errors I never
would have seen, and could never automate no matter how good the CI/CD
might have been. I cannot more strongly recommend this specific set to
others for Go tools and microservices development. In fact, if you add a
cheap Mac to the mix and a Rasperry Pi you have a full ***real*** test
environment. I'm absolutely loving it. A few `scp` and `go install`
commands and I get all the reality I can take.

    #golang #coding #tips
