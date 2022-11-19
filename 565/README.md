# Semantic Versioning Isn't All That Great, Isosec?

The dirty secret from semantic versioning is that *no one* ever actually
fulfills the requirements for a "MAJOR" version update. This is why so
many just use "MINOR" versions instead and the "PATCH" versions for
stuff that is not just to maintain functionality. This was even
something discussed on a GoTime podcast once. I believe the reason is
because semantic versioning, as strictly specified, is actually pretty
broken.

Perhaps the worst example of this is adding `-alpha` or anything. These
resolve *lower* in priority than the same thing with an actual number.
It's very counter-intuitive.

When people see a change, whether it be minor or major, they really
don't grok anything about it until they read the change log. Like a new
version of Dota. They don't care about the update version number, they
need and want to know what specifically changed. That's the priority.
Making arbitrary, unenforceable decisions about the scope of the change
is inconsistent with the needs of the people using the software because
they *must* read the change log to full understand what happened.

I propose a new (perhaps supplemental) versioning system. One entirely
based on the unique second in GMT time that the release happened and
nothing more. These sort well and provide easy unique identifiers for
the specific version. Then, having no implication about the scope of the
change in the version identifier at all, people can read about it
themselves to determine if it is major or minor.

The only downside to this is being able to communicate quickly with
someone about their version. You cannot blurt out the version number,
"Did you try Go 20220323053402 yet?" But this doesn't stop people from
talking about upgrades to Dota2 and games like it. They use terms like,
"the latest".

Obviously, the entire world is deeply coupled with semantic versioning.
But there are many cases where isosec is just fine.
