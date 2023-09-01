# Using tabs for indent in shell/bash

The official way to indent shell/bash code is to use a tab as referenced by the `<<-EOM` operator. I have avoided this because it is inconsistent (even unsafe) to mix methods and very few people have used tabs in shell code before that I have worked with. I'm now committing to using nothing but tabs in shell code going forward (which is also the convenient default of `shfmt`). This means I had to add the following to disable tab expansion in shell.

```vimrc
au FileType sh set noet
```
