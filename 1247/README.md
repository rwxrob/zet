# Use `DEBIAN_FRONTEND=noninteractive` for Scripts

Any time you are doing something in Dockerfiles or scripts that are not
interactive it might be a good idea to add
`DEBIAN_FRONTEND=noninteractive` to turn off some of the verbosity,
logging, and potential prompting. Some packages will even block without
it.
