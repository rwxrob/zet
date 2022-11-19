# Docker Completion Fails Until You First Call It

The common technique of looking up the completion line with `complete -p
docker` fails after you install Docker completion because it is set to
not even load until the first time you attempt to use it with `docker
<TAB><TAB>`. 

```
$ complete -p docker
-bash: complete: docker: no completion specification
```

That means if you have never done that, that your `d` shortcut won't
ever work. 

```
$ complete -p d
complete -o default -F _docker d
$ d <TAB><TAB>
d -bash: completion: function `_docker' not found
$ docker <TAB><TAB>
docker
attach     diff       import     node       rm         stats      version
build      engine     info       pause      rmi        stop       volume
builder    events     inspect    plugin     run        swarm      wait
commit     exec       kill       port       save       system
config     export     load       ps         search     tag
container  help       login      pull       secret     top
context    history    logout     push       service    trust
cp         image      logs       rename     stack      unpause
create     images     network    restart    start      update
$ d <TAB><TAB>
attach     diff       import     node       rm         stats      version
build      engine     info       pause      rmi        stop       volume
builder    events     inspect    plugin     run        swarm      wait
commit     exec       kill       port       save       system
config     export     load       ps         search     tag
container  help       login      pull       secret     top
context    history    logout     push       service    trust
cp         image      logs       rename     stack      unpause
create     images     network    restart    start      update
```

Even though this is a huge bug for Docker to leave out in the open for
so long (my money is on their predisposition to support Zsh including
*forcing* you to use Oh-My-Zsh even though the Zsh team openly advocates
against it, this has zsh stank all over it).

The way around this is to manage your own Docker completion file as I've
done in my `~/.bashrc`.

