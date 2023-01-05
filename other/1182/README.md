# Stop Putting Comments in JSON

Just burned by Windows Terminal when opening the JSON configuration file
and it is full of `//` comments. They are *not* part of the fucking
spec (fucking dumb asses at Microsoft). Adding them makes this file
completely and totally unusable by tools such as `jq` and `vim` (with
highlighting).
