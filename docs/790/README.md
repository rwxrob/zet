# IRL Streaming Kit Conclusions

## Thursday, August 3, 2023, 3:03:45PM EDT

Yesterday I fell on the bike and the shock knocked my SD hard enough that I had to reseat it even though it didn't come disconnected. I've come to know that I just have to pop out the SD card, put it back in, then start the Jetson Nano again to correct the problem. I've heard RationalIRL say that the reason for this is because the extension that my Waveshare case provides just moves around too much to be reliable. I have to agree at this point. Yesterday was at least the 10th time I have had to do that very thing. Sometimes all I do is set the bag down slightly too hard. In fact, if I were not immobile on the bike I'm quite sure this would not be sustainable long-term. I need something better, but there are almost no cases on the market, except for those custom rigs ordered from RationalIRL himself, the one-man company keeping all of OutdoorIRL alive (and out of the hands of LiveU).

* Waveshare case (with wonky extension)  
  <https://a.co/d/idhk4a0>

I just learned (while writing this) that there is a new effort to enable the Orange Pi and it looks very promising <https://belabox.net/rk3588/>. This will completely revolutionize OutdoorIRL if it works.

* No more expensive capture card connection.
* Less power consumption all around.
* Onboard wifi that will receive RTMP (from GoPro and DJI).
* Two ethernet ports so no need for USB dongles at all.
* eMMc memory if SDcard jarring becomes issue.
* Much smaller form factor.

This will allow me to remove the battery from another Verizon modem so I can power it from USB preventing it from ever overheating. The wifi will still allow reusing local wifi when available.

This particular rig will probably allow me to use my GoPro as intended to stream RTMP from the paddleboard without any issues. If and when the GoPro gets too hot I just put it into the water to cool off.

I could even dual stream from two different sources.


## Thursday, February 2, 2023, 11:28:35AM EST

Looking back over two full years of IRL streaming I realize these earlier conclusions led to my current IRL rig, which is by far the most stable, cost-effective, versatile, and small:

* Two TOPK 20w batteries are all you need (but carry two more anyway)
* TOPK 20w batteries USB3 ports *will* die, but it has four total
* Sony AS300 is best IRL streaming camera (cost, etc.)
* Gaffer tape is all I need to protect and cover the AS300
* Tape *everything* to create smooth surfaces that won't catch on anything in bag
* Use a metal piece of tin or something to cover Jetson Nano SD card port (tape it)
* Attach a big-ass USB fan the size of the entire Nano
* Heat issues manifest as other completely unrelated problems
* Over-shoulder (bike messenger) bags are best since can get into them easily
* GoPro mounts are cheaper and more supported than special ones (easily replaced when break)
* Strapping a battery to *front* strap of messenger bad allows lights and charging phone
* Rotating upper arm band best for phone, always with you and TTS hearable
* No need for second "chat" phone
* Mount cam on head support in passenger-seat of car for first-person passenger feel
* People prefer POV in general over "vlogging face"
* Biking is best IRL outdoor activity possible, versatile, but stable and faster than walking
* Walking is fine for shopping and art walks
* Driving is a good time to talk about rig setup and such

----

> 💡
> Lock your phone in 4G! Disable Wifi and Bluetooth.

After more than three weeks researching IRL streaming approaches and
kits I've concluded on the following based on what I plan to do:

* Do most things from my desk, laptop, or lab table with fixed web cams
* Use Rode Go II wireless to go mobile (locally) in the room
* Get VXLR+ to plug Rode into my sound board (XLR) via Cloudlifter
* Use Google Pixel 6 + DJI OSMO 4/5 gimbals when remote
* DJI OSMO 5 has half battery of 4, but extends
* DJI OSMO 4 has 2400 battery that can even charge phone while on
* Having both 4 and 5 compliment each other and allow charging
* Use StreamLabs mobile for everything (1080 @ 30 fps, 2500 bitrate)
* Also use the Rode Go II wireless for wind and interviews
* Use a TRRS splitter on phone for mic and headphones
* Disable Wifi and Bluetooth completely on phone
* Lock phone to LTE 4G (no 5G, the switching kills stream)
* Get an ANKERS battery (mid size), plug gimbal and phone on breaks

For longer trips:

* Netgear Nighthawk 5G (locked in LTE 4G mode)
* Take old phone as backup (with Streamlabs installed)
* Bring one or more substantial batteries MAXOAK (large) when needed
* Bring laptop and stream from that when possible
* Sign up for norip.io (or comparable) service

All the shit people do with LiveU and Belabox is completely and totally
unnecessary. Hitch even said so with a bit of edge in his voice once
when asked saying, "The LiveU is just a big power drain." Most of
Hitch's streams are with a single Netgear Nighthawk 4G hotspot that is
"unteamed" with anything else and he pushes 1080 at 30 fps.

Watching Hitch has made me realize the single most annoying thing on the
road (besides finding a good signal) is battery life. Anything that
burns battery without being needed is a waste. In fact, there is a mount
for bicycle handlebars that holds the OSMO 4/5 so that you can read the
screen while still getting all the unparalleled stabilization without
lost of picture quality. All the digital stabilizers really slam image
quality, yes even the GoPro. Plus, disabling the stabilization makes
your compression faster on your phone (which is basically a wash when
you consider the battery feeding your gimbal). The important thing is
that your phone is worth far less. It doesn't have to superheat to find
a non-existent 5G signal before it bails. It doesn't have to talk to
anything on Bluetooth or wifi. All it has to do is capture and send the
video feed to Twitch. Simplifying everything makes batteries last longer
and everything consumes less bandwidth.

Looking back now I see how completely stupid the idea of using a GoPro
is. I would never have known that without going through all of this. The
ultimate test will come when I run the Turkey Trot with my OSMO 4
holding it to my chest. I already know people are using the OSMO for
cycling and the type of biking I would be doing falls within that
category.

In fact, the only thing I won't be able to do is use both my hands for
anything. I had planned on picking up garbage during my walks and that
could get hard, but I'm still going to try it, one arm will be using the
trash picker, the other holding the gimbal. I suppose that tanks my
wife's ideas for POV porn as well, damn. (We'll get over it.)

Strangely, just using a phone is actually totally fine for
paddle boarding provided I get a mount. The Pixel 6 is 100% waterproof
to something like three meters. I would not submerge it, but it is
apparently fine for splashes and stuff. If and when I do any really
serious water sports, I won't be streaming them. For that a GoPro makes
a lot of sense.

I did discover something else that I *really* want to include in my life
streaming activities: live music sessions. I'll be taking all that
obscene amount of money I would have spend on everything else and
getting a zoom to plugin to my mac or phone. I really want to live
capture great busking music when possible.

Tags:

    #twitch #kits #irl #til
