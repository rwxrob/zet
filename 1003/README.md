# Lowercase JSON / YAML Names Win (I Guess)

As much as I love the readability of uppercase fields in YAML, it would
appear that the sheep have decided. The `yaml.v3` package that
everything is adopting automatically lower-cases all field names (that
start out initial cap so they can be exported). I fucking hate this, but
it is just the way things are. I don't feel like maintaining my own fork
of the YAML package used by all of planet Earth just to be in sync with
this. 

It is even more annoying because the `json` standard package does *not*
lowercase the names so if you want to have marshalling for both JSON and
YAML you just fucking cannot without specifying the lower names of all
the JSON fields.
