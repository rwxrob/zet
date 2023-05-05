# Zwift route achievements are broken in 1.39, beware

The following is what I posted to r/Zwift but the moderators haven't accepted it (and probably won't) so I'm capturing it here. I'll keep new developments documented here.

----

I've done Downtown Titans twice now. Both times captured fully on video during Twitch session. I get to "0 meters remaining" and not credit. First time I rode 30 more minutes, still no credit. Started after last update. Other routes have no problem giving achievements. This is *definitely* a Zwift bug and very annoying. "Support" tells me to empty out files and restart and check my version when the issue is with ZWIFT. I didn't change a thing. Why would a re-install be the official way to fix this? Zwift owes me 2k xp. I don't care as much about coffee stops when the base functionality doesn't even work. I did Four Horsemen two weeks ago (thank god) I cannot imagine dedicating 5 hours and having this problem, but many have repeated this is a problem over and over (and no, I didn't leave, or take a break, or screw up the route, watch the video for proof).

I love Zwift, but I question their priorities and management of expectations. I know it has become a thing to complain about Zwift instead of just being grateful. But I'm also a paying customer who regularly gets other people to also sign up and this makes it hard. In fact, this is the first time I've seriously considered looking at Zwift alternatives out there and I never would have done that before. I was going to do Uber Pretzel this weekend and now I'm just too scared of more bugs, so I'll go outside, or just watch a video and do drops or something.

The proper response should have been to immediately award me the XP after reviewing the video and then say, "I'm sorry for this and your lost time helping us fix our bug. You've been credited the xp, now would you mind helping us identify the problem? If not we understand and thank you for reporting it." I'm pretty sure from from a business perspective Zwift as a company isn't setup to handle this properly at all.

I happen to know this has happened to Zwifters with much more to lose (PRL for example), viewership, and higher profiles. Not bringing this to Zwift's attention would simple be wrong. They cannot improve if they don't know the problems.

By the way, after deleting and reinstalling I still get these all over in my logs:

[0:35:57] WARN : Load Route Warning - Cannot find leadinhighrescheckpoint in data/Worlds/world1/routes/routes36.xml

[0:35:58] WARN : Load Route Warnings - Cannot find decisions in data/Worlds/world1/routes/routes75.xml. Is this intentional?

I suspect the reason is because in order to get 1.39 you first have to install the other version and somehow those data files are not compatible between the old version and the new one. I've now gone through the uninstall, remove Program Files/Zwift and Documents/Zwift, and had the upgrade detected and added and the logs are still filled with tons of "can't find route" errors. Bottom line: don't do any route achievements until they fix this. I'll post the routes that are broken (base on number in the logs) soon.
