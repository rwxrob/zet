# Use `strings.Builder` and not `bytes.Buffer`

Often you will run into situations where you need to provide an `io.Writer` implementation and really just want a string out of it, for example, when dealing with `crypto/ssh.Session.Stdout`.

Most of the time you probably want `strings.Builder` instead of `bytes.Buffer` but understanding the difference is important.

> A Builder is used to efficiently build a string using Write methods. It minimizes memory copying.

* 7 notes about strings.builder in Golang \| by Thuc Le \| Medium  
  <https://medium.com/@thuc/8-notes-about-strings-builder-in-golang-65260daae6e9>
