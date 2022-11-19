# Reaching Single `COPY` Nirvana in Dockerfile

Someone had to point this one out to me. It's not intuitive. It says to
*overlay* everything in `./files` over the top of `/`, that's what the
trailing `/.` is about. Then, add the Dockerfile for reference.

```dockerfile
COPY ./files/. ./Dockerfile /
```
