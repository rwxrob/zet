# 42 Crunch (JSON-Schema) `maxlength` is Unicode not bytes

We found out that the validation of field length is in Unicode code points. This is consistent with what Go does for `len` operator (thank God, so many other languages get this wrong, including Python, JavaScript/Typescript, Java, C/C++ and others). So long at the type is a `string` and not `[]byte` slice Go does the right thing.

It's worth mentioning that a regular expression checking for length would always fail here because the length of a span is *always* in bytes and not Unicode, unless a second match were done just using the newer `\P{}` and `\p{}` syntax for Unicode.

## ChatGPT response

The "maxlength" keyword in JSON Schema specifies the maximum length of a string value. It is defined in terms of UTF-16 code units, not in terms of Unicode code points or bytes. Each Unicode code point can be represented by one or two UTF-16 code units. Therefore, the "maxlength" keyword reflects the maximum length of a string in terms of UTF-16 code units.


