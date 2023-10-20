# Git commit conventions: https://www.conventioncommits.org

Update: Friday, October 20, 2023, 8:19:40AM EDT

* Trying to have one issue per commit
* Started adding `fixes #1` and such to the end of commit messages
* Wrongly used `fix(1)` instead of `fix(ssh)`
* Mostly use `fix` and `feat` now
* Need to start using `doc`, `refactor`, `style` and `chore` a lot more
* Noticed how well all of this pairs with [`gh issue develop -c`](/2388)

Related:

* Mastering Git: The Power of Conventional Commit Messages \| by Amirhosein Gharaati \| Sep, 2023 \| Stackademic  
  <https://blog.stackademic.com/mastering-git-the-power-of-conventional-commit-messages-1bfbd1cae2c2?gi=f10198dca24f>

----

* Conventional Commits  
  <https://www.conventionalcommits.org/en/v1.0.0/>

Update: Wednesday, June 21, 2023, 2:02:44PM EDT

I've been swooned into using the <https://www.conventionalcommits.org> practices because the ArgoCD and other projects use them to great effect when preparing automated release notes from the messages. This trumps the simpler conventions used up to now.

----

Can't find where I read it (long ago) but here are the conventions I follow specifically for Git commit messages. You'll find these are standard in any project that has a clue (which does not include most Node projects):

* Never longer than 50 characters
* Answer phrase "If I commit this patch it will ..."
* No end punctuation

I *never* include merge commit messages. I refuse to clutter my commit log with stuff that makes no  sense.
