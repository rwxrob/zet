# Have Someone Experienced Review Your Code

Even if no one requires it of you, make sure you have someone else that
you trust review your code regularly. It's not just to save your ass
from making a huge mistake, it's to get another person's opinion who
might see something you don't. 

This is especially true before releasing anything into production. I've
recently seen several things go into production that did not have a
single person other than the author review. That's fucking stupid and
dangerous and usually against the policies of most development shops and
operations groups. You might think it's just a little script to do this
one little thing --- to prod. But, in fact, it's exposing the entire
organization to a huge risk and should be at least vetted by one other
person, preferably a senior.

This isn't about control or politics. It's about responsibility and
learning. I jump at the chance to have someone point out something I've
done in a way that is suboptimal even if it hurts my ego a bit. Don't be
that person who gets offended at every suggestion to reduce a few levels
of nesting in your gawd-aweful algorithm. 

## But What If I Can't Find Anyone

Sometimes you don't have anyone. In those cases, find a person who
writes similar code online who is trusted by many and then find another
person like that. Then read through their code regularly. Then ask
yourself, "Would so-and-so write this like this?" I find myself asking
that as I imagine if Rob Pike were reviewing my code. I do it so much I
actually have dreams about it, weird, I know. Like my favorite dream
these days has nothing to do with sex, it's Rob Pike telling me he
thinks my code and approach is beautiful, in his little way, with a nod
of acceptance even if the reality is that my Go (and certainly C code)
are so phenomenally far from anything he's nod at that I'm eternally
motivated to improve. I do think he'd like some of my approaches,
however, although I'm pretty sure he would replace the entire CmdBox
`init()` and `Register` approach with highly-optimized code generation instead. Humm, I need to look at that again.
