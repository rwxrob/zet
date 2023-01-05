# Info Nodes in Single File

Thinking YAML might not be best for info nodes. Just a plain old
markdown file beats YAML for parsing speed without needing a database,
and could easily be imported into a database if and when needed.


```
# lorem

Lorem [ipsum](#ipsum) dolor sit amet, consectetur adipiscing elit, sed
do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit
in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint.

# ipsum

Just so much easier to write and maintain this way.

```

Humm, I wonder how that renders.

    #edtech #infonodes
