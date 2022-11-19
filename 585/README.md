# Use `i` and `a` Frequently in Vim

The most powerful Vimism I've allowed myself to really burn into my
muscle memory lately has been `i` and `a` and all the combinations with
everything else. This is every bit as powerful as macros (another Vimism
I've been shamed into using). Try out these combinations to see why:

```
dap  - delete around current paragraph
dip  - delete current paragraph
diw  - delete current word
daw  - delete around current word
diW  - delete current larger word (ex: --foo-bar)
daW  - delete around current larger word
yap  - yank around current paragraph
yip  - yank current paragraph
ea   - append to current word
cw   - change to end of current word
ciw  - change current word
caw  - change around current word
dw   - delete to beginning of next word
daf  - delete current function
yaf  - yank current function
dif  - delete current inner function
yif  - yank current inner function
dd   - delete the current line
gwip - wrap the current paragraph
gwap - wrap around the current paragraph
>ip  - indent the current paragraph
<ip  - dedent the current paragraph
!ip  - send the current paragraph to shell command
```

For the record, these Vimisms do not impact my ability to be wicked
productive with `vi` if that is all I have as well (which is almost
never these days --- especially now that we can mount containers and use
whatever editor we want more than before).
