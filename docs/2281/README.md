# ChatGPT is full of shit

As much as I like it, shit in means you get shit out, and since ChatGPT is sourced off stuff on the Internet you can be sure you are going to get slightly better than StackExchange answers that should always be verified with the specifications where possible. Here's a solid example.

```sh
$ ?? are plus sign ascii characters allowed in the url schema portion
No, plus sign ASCII characters (+) are not allowed in the URL schema portion. The schema
portion of a URL, also known as the scheme, is used to specify the protocol or
type of URL. It typically does not contain any special characters, including
plus signs.
```

This is dead wrong according to <https://tools.ietf.org/html/rfc3986>:

```abnf
URI           = scheme ":" hier-part [ "?" query ] [ "#" fragment ]
scheme        = ALPHA *( ALPHA / DIGIT / "+" / "-" / "." )
```

Clearly the `+` is accepted which I already knew because there are so many URIs in use that have them. Even ChatGPT seems to "know" them:

```
$ ?? examples of URIs that have pluses in the schema portion
1. ftp+ssh://example.com
2. magnet+udp://example.org
3. rtsp+http://example.net
4. git+ssh://github.com
5. sftp+ftp://example.io
```

People need to *seriously* stop trusting any ChatGPT answer without getting confirmation. It really is only slightly better than getting a StackExchange answer.

