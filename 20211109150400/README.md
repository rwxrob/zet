# Send Only Mic to Twitch VODS (no music) with OBS

While it is rather simplistic for most setups, just turning off "Desktop
Audio" from all Twitch VODs is enough for many live streams where I want
to listen to music in the background but want it removed from what gets
saved to Twitch. The steps are really easy:

1. Settings - Output - Enable Advanced Encoder Settings
1. Settings - Output - Twitch VOD Track (Uses Track 2)
1. Audio Mixer - Desktop Audio - Advanced Audio Properties - Tracks - 2 (off)

It's easy enough to turn back on for gaming and such that would
otherwise be removed.

There are fancy ways to send the audio of only Spotify (or something) to
another pseudo-audio-device so that it is all that is omitted, but that
will have to come later.

Tags:

    #sound #obs #vods #livestreaming #tips
