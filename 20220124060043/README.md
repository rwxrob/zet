# Important Repos Every Tech Should Have on GitHub

GitHub is the most effective way to supplement your individual job
searching with a portfolio of what you have done and currently love to
do, yes even if you are an operations geek instead of a software
engineer. But, what are the common repos that allow you to *never* have a
LinkedIn account at all?

* `<user>.github.io` This is your personal GitHub Pages web site. Use it
  as your landing page on the Web, which will primarily point to your
  GitHub repo. You should eventually get your own domain name and point
  it to this (for free). All other repos that have GitHub Pages will be
  routes under this domain (ex: `zet` -> `https://<user>.github.io/zet`,
  `https://rwx.gg/zet`)

* `<user>` This repo contains the README.md file that is used for your
  GitHub landing profile. It includes a `.github` sponsors file and
  other information about your favorite repos and such. You can link a
  welcome video as well. Consider this a supplement to your main web
  landing page. Some of it will definitely overlap with your web repo.

* `dot` Having a "dotfiles" repo has become something of a rite of
  passage. Without it you cannot share and show off your cool terminal
  and Vim configurations to the world. This is essential when people ask
  you "how do you ..." questions and you want to quickly get them to the
  answer without fumbling around for where you save it. Always use the
  `setup` or `install` script approach since that gives you the most
  flexibility. Do *not* directly link it and avoid stupid tools like
  `stow` that are completely unnecessary and less in your control.
  Remember, you are showing off your scripting skills here, not your
  knowledge of useless shit someone else made. Your `dot/scripts`
  directory should have all your quick and dirty scripts, `dot/snippets`
  is a good place to store your code snippets, `vim`, `tmux`, `bash`,
  `lynx` and other application specific directories can have their own
  `setup` scripts that are called from the main one and make it easy to
  find. Having an `installers` directory makes it easy to keep track of
  everything you need on install that tends to not fit into your pretty
  package management solution.

* `zet` This is your zettelkasten repo. Some people call it their
  "second brain". It is where you dump every thought you have (that you
  can share publicly). Each directory is numbered after the GMT "ISO
  second" and contains at least a README.md with the header title on the
  first line. (Never any "front matter".) Each README.md should be
  relatively short and contain one specific topic. You might opt to
  include one verbatim (4 space indented) section at the very bottom
  containing one key = value label pair per line and a final line with
  hashtags for better organization, meta data, and querying later. Read
  more about Niklaus Luhmann's Zettelkasten method for more about
  organization.

* `lab` This is the equivalent of a black notebook or "code book" or
  coding sandbox like many veteran system administrators and hackers
  have always used. This is where you put all our your successful (and
  failed) explorations of different topics and technologies. We organize
  everything into sub-directories for easy searching with `find` or
  GitHub's built in search capabilities. Each lab session can have it's
  own README.md or one that you continue to update with different logged
  events. Write your discoveries and anything that you need to retrieve
  quickly in your `zet` and refer directly to your `lab` in your Related
  section. Other artifacts from your `lab` research will become
  substantial repos of their own that are added to your `cv` as examples
  of your work. You can choose to keep your `lab` public or private.
  Either way, make sure to explain in the main README.md what you are
  doing so people don't mistake this exploration as anything serious.

* `cv` This is were your resume goes, except we call it a CV because we
  are going to put everything about your career (that can be public)
  into it and create methods for trimming that content down into
  specific resumes when needed.

* `~/Private` This repo should not be on GitHub, but should instead be a
  clone of a local "bare" (`/media/myusb/priv.git`) Git repo saved on an
  external USB stick that can easily be grabbed at any time. Consider
  using the `~/Private` location for it so you can easily navigate to
  it. This repo contains all your tokens, certificates, and other
  secrets. Create an `install` or `setup` script (like `dot`) that is
  meant to run after the `dot` install to overlay your system quickly
  with the private and personal stuff. Consider maintaining a private
  `Private/zet` in here as well for notes that are note suitable for the
  public.

Other common repo naming conventions you might consider include:

* `cmd-<name>` Consider using a `cmd-` prefix for all your significant
  scripts that extend beyond what is practical to maintain in your
  `dot/scripts` directory.

* `template-<name>` Having a template repo for the types of repos you
  tend to create often and quickly is nice to get you started without a
  lot of scaffolding, for example, for your bigger bash scripts that
  already have command-line tab completion in them.

Keep in mind when naming things in your GitHub repo that other people
will want to fork it and if you pick too generic of a name that it will
likely conflict with something else they have already forked. That's
their problem and not yours, but it doesn't hurt.

> 🤬
> For the love of God, stop creating camel-case repo names (ex:
> SomeThing) Prefer dashes over underscores as well. Remember every repo
> name becomes a potential URL.

Related:

* [20210502004642](/20210502004642/) ZettelRepos, Zettelkasten with Just Git and GitHub
* [20210502062346](/20210502062346/) Power Searching with Zettelkasten and GitHub
* [20210502161423](/20210502161423/) GitHub, Your Best Home on the Web
* [20210502202327](/20210502202327/) Preserve Your Knowledge in GitHub Arctic Vault
* [20210506151955](/20210506151955/) GitHub `gh` CLI Tool Defaults to HTTPS
* [20210519171100](/20210519171100/) Put It All on GitHub
* [20210623164553](/20210623164553/) Gamified GitHub
* [20210809015157](/20210809015157/) GitHub Repo Directory Naming Conventions

    #tips #git #github #lifehacks
