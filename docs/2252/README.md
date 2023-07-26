# Do not use Twitter! (Don't even open it)

Was reminded after losing 20 minutes of my life following rabbit holes posted by clueless people that there is nothing I want to read (mostly because of complete and total lack of any basic relevant experience). Here's an example:

```vim
if has('python3')
  function! Guid()
    let l:guid = ''
python3 << EOF
import uuid, vim
vim.command(f"let l:guid = '{uuid.uuid4()}'")
EOF
    return l:guid
  endfunction
endif

inoremap <expr> <c-g> Guid()
```

That's right, not only do you have to have Python installed for this to work, but you will now be burning C-g into your muscle memory, so *fucking* stupid.

I replied:

```vim
!!uuidgen
```

I'm quite certain this person---who maintains an account labeled for their Vim expertise---has no fucking clue what I'm talking about. (And I'm sorry, I just have to say *fuck* in this rant. I can't not.)

Here's another one:

> Damn it! emacs embarrassed me in front of our lead engineer yesterday. It crashed when I pasted a huge chunk of json, and I had to resort to nvim.

The level of no-clue-at-all in that tweet is completely astounding. Using a text-editor buffer to transfer a "huge chunk of json" is something only the least experienced noob would even attempt.

In a way I'm glad. I haven't read more than a single tweet in the last two months and my life has been so much better because of it. People who religiously post shit to Twitter in the hope of drumming up "community involvement" are going about it entirely wrong.

Last night someone I newly followed on Twitch posted this, "The smarter you are, the less you talk." I couldn't agree more. But I wonder where all this self-soothing writing falls into all that. One thing is for sure, the people who are *way* smarter than me say very little and wouldn't be caught dead streaming on Twitch, so what does that say about me. \*sigh\*

