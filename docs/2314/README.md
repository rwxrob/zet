# Controlling OBS with Websockets

Yeah, you can control OBS these days (even on Linux) through Websockets. The API is pretty simple to use with `goobs` library (which is auto-generated from the Websockets protocol definition. Combining all of this with Bonzai no-opts, speakable interface makes converting bot commands seen from a mod into direct OBS commands absolutely trivial. The usage of the `!obs` command is *identical* to that from the command line on that system itself.

First tests are available at <https://github.com/rwxrob/obs> but will need an `obs conf edit` to add something similar to the following (which are obviously safely localized):

```yaml
servers:
  default:
    address: 192.168.1.6
    port: 4455
    password: Mpq6dNXVAlfpJJLp
```

This is going to make replacing NOALBS absolutely trivial as well (which I've come to accept and appreciate but really despise).

This is going to enable some pretty cool streamer stuff:

* Starting/stopping the stream remotely.
* Activating/deactivating a sound source remotely.
* Spending channel points for live screenshots.
* OBS based user interactions such as quizzes and stuff.
* My own implementation of "Stickers" that is channel points based.
* Multiple room camera angles controlled by the users in chat.

## Related

* GitHub  
  <https://github.com/obsproject/obs-websocket>
* Official Documentation  
  <https://websockets.readthedocs.io/en/stable/index.html>
