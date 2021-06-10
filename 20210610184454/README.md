# Is the Future About Code Generation?

I can't fully remember where I read it. I believe it was Rob Pike who
mentioned that the future of applications development will ultimately be
about code generation. I could not agree more. Recently, I was writing
about [Swagger] and round myself reminded of that point. It was one of
the main reasons behind [PEGN] and why I need to finish it. It is
related to my work on [CmdBox] as well, although that is more about
writing composable code more than generating it, even though the
scaffolding is created through a GitHub template and eventually with the
help of a `cmdbox` command line utility. I also recently read about
Svelte when someone made that point that its ultimately claim to fame is
that it generates vanilla JavaScript rather than doing anything
complicated in the browser (like React does). The code generators for
the Unicode libraries in the Go language come to mind as well. I wonder
if static compilation is going to make code generation even more
palatable. Personally, I wish more attention had been placed on that
instead of adding "generics" to the language. In a way, C++ templates,
C macros, and generics have been a form of code generation from the
beginning, which reminds me that code generation conversations quickly
become conversations about meta-programming, and those can spiral out of
control really quickly. Still, we need to think about this stuff,
because eventually, that is where things are going. Machine learning is
threatening to replace coding entirely in some not-so-dystopian future.
But the machines doing the learning will need meta-programming policies
to apply. We already see this in a small way in Kubernetes. So much of
what it does to provision and orchestrate would have been coded before.
Now you just set policies. There's no code generation, but it's sort of
implied.

[Swagger]: /20210610183738
[PEGN]: <https://pegn.dev>
