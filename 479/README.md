# YAML is Still Better Than JSON for Humans

It's rather trendy to hate on YAML these days, what with all the "YAML
Programmers" out there. But YAML is still the most human friendly
language for the type of voluminous declarative configuration data it
handles, even more so now that `yaml.v3` Go package insists on
four-space indent for the defaults. This will push out indentation to
the point were people will break up stuff into more modular YAML files.
It's the reason that six-space indent is *not* a bad thing. It forces
you to rethink that extra unnecessary nesting and do it better.

A few weeks back I was predicting that something better would come along.
But I don't think that anymore. Just heard the creator of Porter talking
about that on the Go Time podcast. People think they want "convention
over configuration" which means they want logic in their templates and
configuration files, they really fucking don't. Adding that means you
get another layer of abstraction and gets all complicated and ends up
with another declarative wrapper around it.

So stop fucking complaining about YAML and embrace the joy that is
allowing you to put comments in your code, allowing well-formed and
readable block paragraphs of text, and protecting you from typing all
those double quotes that you would be otherwise typing to do this all in
JSON, or worse XML. 

In fact, after reading a recent take down of TOML I can't even get
behind it anymore (even though I made the logo). TOML creates a
disjointedness that causes confusion in larger configurations. YAML
hides that --- especially the way people use it today (without the
pointers and dereferencing).
