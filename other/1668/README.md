# VirtualBox Vagrant Provider Uses Subcommands

It might be obvious to everyone else, but it wasn't to me. When you see
the following, it is the subcommand to the main `VBoxManage` command:

```
unless File.exist?(disk)
  v.customize [
    'createhd', 
    '--filename', disk,
    '--variant', 'Fixed',
    '--size', 20 * 1024
  ]
end
```

So in the above `createhd` is actually `VBoxManage createhd` (and yes,
you have to fucking include the proper case).
