# Adding cache check bad idea in packrat PEGN parser

The `Rule.Check` should not have to burden itself with checking the cache, that should happen before it gets called. This also incredibly simplifies the structure of all `rat.Check` functions allowed them to be grouped into a module/package without any grammar association at all.
