# Anything but `twitch-cli` and you are doing it wrong

I have been absolutely blown away by the <https://github.com/twitchdev/twitch-cli> project which includes an almost fully implemented "mock-api" server.

First start up the server in a dedicated `tmux` window/pane:

```sh
twitch mock-api start
```

Here's a script to get the mock ClientID:

```sh
#!/bin/bash
curl -sS -X GET http://localhost:8080/units/clients | jq -r '.data[0].ID'
```

And ClientSecret:

```sh
#!/bin/bash
curl -sS -X GET http://localhost:8080/units/clients | jq -r '.data[0].Secret'
```

And an application token:

```sh
#!/bin/bash

curl -sS -X POST "http://localhost:8080/auth/token?client_id=$(twitch-mock-clientid)&client_secret=$(twitch-mock-            clientsecret)&grant_type=client_credentials" | jq -r '.access_token'

```

And then you can do all sorts of really cool shit:

```sh
#!/bin/bash

curl -sS -X GET 'http://localhost:8080/units/users' \
-H "Client-Id: $(twitch-mock-clientid)" \
-H "Authorization: Bearer $(twitch-mock-app-token)" \
| jq -r '.data.[].login'
```

I just want to repeat how cool this is for doing live Twitch API development stuff because I never have to fear doxing any of my own stuff or even obsessively creating a bunch of pseudo accounts on Twitch to do the things I want. It's still in beta, but this is definitely a great direction for them to go, so long as they also use it themselves, which I'm thinking is the reason they created it in the first place.
