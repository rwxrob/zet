# Personal gateway server

I've found that having a personal Ubuntu Linux Server accessible from anywhere on the Internet to be the best way for making small code changes to personal repos including zettelkasten entries. This way even from a work computer I can ssh into it to write down a thought or make a tweek to my dot files repo without needing to do anything but pull down those changes to whatever other system in a read-only way.

## Legal considerations

There might be a legal interpretation that would say that because I used my work computer to ssh into my gateway system that all the IP legal ownership things would apply, but that would be quite a stretch and one that I would be willing to fight out in court. Using ssh to connect to a personal server is no different than reading or using Gmail or a personal Web service of any kind from a work computer. While there are many very real reasons not to do that—the biggest being lack of trust for an employer not to access that personal information—the convenience of being able to ssh and make zet updates is worth it to me.

## Digital Ocean

Digital Ocean continues to be my provider of choice. They are super easy to use and very affordable. The DO UI is the best in the entire market.

## Cost

It cost $6/month for a very small server, but all I need is a small server to access via the terminal and it will never be serving up anything, ever. This is only for writing and quick code tweaks and testing, not for heavy duty kubernetes development and testing.

## Freedom

I started using a gateway server again while considering digital nomad life by bike. I wanted to be able to login to something and do mostly writing. Even though I gave up the dream of being a digital nomad by bike (which is impossible for a systems operation person who is paid for being reliably available) I am enjoying the freedom to attach to my gateway from any computer in the world. So long as I trust a computer, I can use any computer to connect, anywhere.

## Reliability

During the move I took down my servers in the apartment. This meant for much of it I was unable to test stuff out and write. This is normally okay for most people because they are pretty stable, but for someone moving around a lot having the stability of a cloud provider makes a lot more sense.

## Less invasive than VPN

Most people use a VPN for this stuff, but being able to just ssh into a personal gateway is way better. For example, I cannot install a VPN onto my work laptop, but I can use ssh to connect to my personal gateway. A VPN does make sense when needing access to sever home-lab systems all at once and when doing it from a personal laptop, but it makes no sense at all if I want to be able to access it from any computer in the world.
