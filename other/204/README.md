# Fix For Bullshit WebDev Bug in Spotify

Shitty web developers strike again. Spotify absolutely sucks as a
graphic user application. It is so fucking buggy. This time when
clicking on a "currently playing" song it should jump to the song in the
current playlist but gets it entirely wrong. This has happened at least
six times to me over the last two weeks. It is a critical user story
because it is the only way to create a playlist of any significant size
because you regularly have to jump to the currently playing song to
delete it and update the list. The web is full of people screaming about
this shit in Spotify's production code but they either don't care or
don't have the ability to fix it, probably because all the people they
hired went to web development bootcamps. Pretty much every application
that has a serious bug in my life (Discord is another *huge* one) comes
from bullshit web development shops and people who don't have even the
slightest clue what the fuck they are doing. They make Microsoft look
like a shining example of production software quality. By the way, the
fix for this is somehow to attach to the web version (which doesn't even
have the fucking ability to click to go to song at all) and then reopen
in the app running locally. That fixed it for me. Blowing out all your
cache and/or reinstalling the entire fucking app fixes it as well.
