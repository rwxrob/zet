# OCMS Credentials (Badges) Specification

This is the specification for Open Credential Merit System credentials,
informally referred to as "badges". OCMS ("Occam's") badges are central
to OCMS itself. (See <https://ocms.cc> for more.)

> 💬
> Use the term "credential" when listing badges earned on resumes and
> other formal education and training sections. Use the term "badge" to
> save time when discussing credentials informally.

Each badge is composed of meta data and layered requirements separated
into distinct YAML documents within a single file separated by the
standard YAML document separator (`---`) for all but the first (meta
data) section. However, unlike YAML the meta data first section must not
contain any blank or commented lines and must not begin with the YAML
separator and the first line must be the `ocms` meta data property (ex:
`ocms: v1`. This allows applications to quickly determine the state of
the credential specification without necessarily downloading the entire
file which allows OCMS registries and discovery tools to automate
updates regularly.

The file is named after the base portion of its URL followed by an
optional version and language identifier and mandatory `.yaml` suffix
(ex: `unix-fr.yaml`, `unix-v1.1.34-fr.yaml`). English is the primary
language for all OCMS credentials and is therefore assumed if no
language identifier is included in the file name (ex: `unix.yaml`). See
the `lang` and `version` meta data definitions below for more.

The first YAML document within the file (`.[0]`) contains the following
meta data:

> 💬
> Meta data identifiers will never exceed seven Unicode word characters
> allowing them to be always easily readable on one line from any
> terminal.

> 💡 
> Use `yq e file.yaml | jq -s '.[0]'` to access, for example, only the
> meta data YAML document within `file.yaml`.

`ocms` (required) identifies the version of the OCMS credential data
schema. It must always be the first line in the file and will almost
always be exactly the same. This allows potential changes to the
organization of the YAML file itself to change over time without
impacting applications that have been built expecting a specific format.

`name` (required) is a simple, succinct name (no more than 30 Unicode
word characters) in the specified language that conveys the core topic
of the credential/badge. This may include multiple words, but single
word names (including acronyms) are strongly encouraged (ex: Linux,
Sculpture, 3D Modeling, YAML). The `name` should combine well with the
single word names for the `levels` (ex: "UNIX Basics", "UNIX Essentials",
etc.)

`url` (required) is the universal resource locator which must be
a unique web address pointing to base directory containing the YAML
files (ex: `ocms.rwx.gg/unix`). The URL may contain any valid URL
characters including sub-directories (though discouraged since these
will be used as `prereqs`) but the final directory must exactly match
the base name of the main English OCMS credential specification file (ex:
`ocms.rwx.gg/unix/unix.yaml`) and contain only ASCII lowercase letters,
numbers, or underscore (`[a-z0-9_]`). The URL must be accessible
publicly with simple tools like `curl` and the schema portion of the URL
must be omitted (and is assumed to be `https` or `http`).

> ⚠️
> It is vitally important that the `url` of a badge *never* change. Put
> great thought into it including who will inherit the domain name
> beyond the lifetime of the original author. For all intents and
> purposes, any change to the `url` constitutes creation of a *new*
> badge specification. Though not as succinct, often the use of
> a hosting service domain such as `github.io` may be preferable due to
> its permanence.

`issues` (optional) provides the URL home where issues including errors
and suggestions may be submitted by the public. This should be more than
just a web site and will usually be the web address of a source hosting provider, but not always. The `https` or `http` schema portion may be omitted and will be assumed.

`version` (required) is the semantic version of the credential itself.
Only major versions should be trusted by those wanting to follow them.
Minor version changes should only be for *adding new optional
requirements* (never for removing or changing base requirements). This
fulfills the "non-breaking changes" idea of semantic versioning. The
patch version changes will be very frequent since they relate to the
simpler things like grammar and spelling fixes and such without changing
things like identifier names and other things in the minor version
scope. For convenience, any previous version of an OCMS credential
specification file may be included along with the current one provided
the version is added in the file name immediately after the base name
and preceding any language portion separated by a single dash (ex:
`unix-v1.2.34-fr.yaml`). The most recent version, however, must never
include the version in the file name.

`lang` (required) is the HTML ISO language code known best for its use
in the `<html>` tag. For consistency, all OCMS credentials should first
be written and maintained in English. This prevents misunderstandings
due to translation. All supported languages must be maintained at the
same location in order to preserve the same URL, but all languages
*other than English* must each have their own file with the `lang` coded
added with a dash to the base portion of the file name (ex: `unix.yaml`
and `unix-fr.yaml`).

`levels` (required) is an array/list of names for each level
corresponding to the following YAML sections of the file. Each name must
not exceed twelve Unicode word characters and may not include any
punctuation or whitespace. Level names will be added to the base `name`
to quantify rhetorical references to specific credential levels (ex:
`UNIX Basics`). All credentials are required to have at least one level.
There is no specified maximum number of levels. Badge creators may
decide how they wish to define the distinction between badge levels.
However, it is strongly recommended to limit the number of levels to
five using the following scale, scope, and names for consistency and
reduced complexity:

1. Basics (conversant, has sampled and mastered something minimal)
1. Essentials (working knowledge, just enough to explore and be dangerous) 
1. Proficiency (full professional proficiency, employable)
1. Excellence (beyond proficiency, innovative application of)
1. Mastery (domain leader, able to instruct and expound about)

For convenience, the name "Proficiency" can be dropped since that is the
default assumed level. The other levels are either remedial or
exceptional to base, professional proficiency.

> 💬
> Limiting scope and depth is a challenge facing all learners (as well
> instructional designers). "How much should I learn?" Creating levels
> answers this question with another: "How much do you need to learn?"
>
> This distinction of levels also best accommodates the need for
> inter-dependencies. One credential might require that only level one
> be completed before attempting it. Another might require a full (level
> three) proficiency instead. This clarity makes navigating an otherwise
> complex set of learning requirements relatively easy, even fun since
> it adds an element of gamification to the learning process.

Each level is composed of a non-rooted tree of requirements; there may
be more than one top-level requirement and every requirement (at any
depth) may have one or more sub-requirements.

```yaml
prereqs:
  - [ ocms.rwx.gg/computers, 3 ]
philosophy:
  onebest:
  integration:
  filters:
  textual:
scripting:
  posix:
  variables:
    types:
      numbers:
  conditions:
```

The optional, reserved `prereqs` requirement (which is first by
convention, if included) contains an array/list of other OCMS
credentials by their `url` and `level`. These credentials must be earned
before attempting the credential level containing the `prereqs`. Upper
levels of a single badge assume a `prereqs` entry for all the previous
levels for that same badge. They do not need to be listed.

All other requirement entries use their own identifiers. Each
requirement identifier must contain only lowercase ASCII alpha
characters and the underscore (`[a-z_]`). Numbers are not allowed.
Requirement identifiers beginning with underscore indicate that the
requirement is to be temporarily ignored either because it is being
prepared or recently deprecated. Temporary identifiers should be
removed completely within a reasonable amount of time. Simple,
single-word identifiers are preferred for their mnemonic value. A single
underscore may be used to separate one or more words in the identifier,
but multiple words should be avoided whenever possible.

> ⚠️
> Remember, potentially millions of learners will be referring to badges
> and requirements by their identifiers so picking good, mnemonic ones
> is a critical priority --- especially given their permanence. Be
> careful to pick identifiers that are full English words that can be
> recognized by conversational user interfaces.

Each requirement has the following reserved key/value pairs:

`line` (required) contains a single line of no more than 50 Unicode word
characters in plain text (no emojis allowed) describing the requirement
as it would be listed as a bullet point in a resume, job description, or
presentation. It must begin with a capitalized verb, use sentence case,
and not end with any punctuation at all.

`text` (optional) contains a single paragraph of no more than 500
Unicode word characters of CommonMark markdown text describing the
requirement. This text is primarily intended to help remind the learner
and mentor what the requirement is about. Additional explanatory text
should be maintained outside of the OCMS credential specification itself
in a site, PDF, or pamphlet.

> ⚠️
> Consider carefully what is added to the requirement. Any change, even
> a minor change in grammar or spelling correction must always trigger
> a version change. When in doubt leave text out and maintain such
> explanatory documents outside of the credential specification.

`time` (required) is the estimated number of hours the average learner
would require to complete this specific requirement. Decimal numbers are
allowed (ex: 0.5 is half an hour).

`xp` (required) is the number of experience points awarded to those who
finish this requirement. Experience points provide a measure of weight
and importance.

> 💬
> The Beginner Boost Badges are OCMS Credentials grouped and associated
> with the rwxrob.tv Beginner Boost series of videos.

Related:
* [20210718164932](/20210718164932/) Boost Badges
* [20210924134227](/20210924134227/) Boost Badges: Levels
* [20210927202107](/20210927202107/) Boost Badges: Level One, Basics
* [20210927210030](/20210927210030/) Boost Badge Requirements and Bloom's Taxonomy
* [20210928135220](/20210928135220/) Boost Badges: Level Three, Proficiency
* [20210928143408](/20210928143408/) Boost Badges: Level Two, Essentials
* [20210928144508](/20210928144508/) Boost Badges: Level Four, Excellence
* [20210928144751](/20210928144751/) Boost Badges: Level Five, Mastery
* [20210929113346](/20210929113346/) Merit Badges Provide Breadth Without Fear
* [20210929115923](/20210929115923/) Merit Badges Fail to Provide Depth and Repetition
* [20211005135001](/20211005135001/) Resolving Problems with Badge "Requirements"
* HTML ISO Language Code Reference  
  <https://www.w3schools.com/tags/ref_language_codes.asp>

Tags:

    #ocms #edtech #spec #todo
