# The Go YAML Package Discards String Quotes

While doing testing today and transforming a model struct from file and
outputing into YAML using `cmdbox.ToYAML` I noticed that tests failed
because the marshaller in the YAML library decided to through them out
apparently because they are not needed.

