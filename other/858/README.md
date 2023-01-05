# Everything Wrong with OpenAPITools `go-server` Generator

* ***Depends on "unmaintained" `mux` router package***
* Default to 1.13
* Use of deprecated `ioutil` package
* Use of TODO for implementation instead of side-effect imports
* Failure to match Go style guidelines and naming conventions
* Use of log4j (probably fine since internal)
* Use of Java 8 (current is 18)

## Conclusions

* Trying the `go-gin-server`
