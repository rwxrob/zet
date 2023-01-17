# Oh yeah, I FUCKING HATE Hugo!

Hugo has such a completely ass-backward design from the very foundation (but still so much better than all the JavaScript and Python and Ruby alternatives). No one reading this will take me seriously until they have tried to use it. It is a shining polished turd of an application, and an eternal testament to over-engineering.

* Why the fuck to I have to `hugo new site .` and then edit layout files rather than MD?
* Why the fuck did they depart from simple Go templating? (`{{< >}}`, `{{% %}}`)
* Why the fuck is it nearly impossible to rip the blog-centric design out?
* Why the fuck did Hugo go with `_index.md` instead of the standard `README.md`?
* Why the fuck does Hugo insist on being the most important thing in the repo?
* Why the fuck doesn't Hugo put the content first?!
* Why the fuck doesn't Hugo have a sane domain model?
* Why the fuck is it nearly impossible to create data-centric "pages"?

I'm so glad I have been forced to use this lately to realize how completely fucking stupid Hugo really is. I'll definitely be taking all that anger and stuffing it into motivation to make KEG static rendering so much better. A better design is a static site generator that is built around the concept of API requests without the API, where every fucking resource on the site is a part of a data model, and where those models have views.

Hugo is *exactly* what happens when the developers are not kept in check by their users, when they make whatever the fuck they think the users want, and don't give a shit about what they really need. It is the *opposite* of "do one thing well" and the reason that TJ Holowaychuk (refuses to use it even though he's a huge Go advocate and much nicer than I am).

* <https://github.com/rwxrob/hugo-tutorial-link-data-to-type>
