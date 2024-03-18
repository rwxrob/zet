# Programming Humans: documenting procedures for human consumption

Sunday, March 17, 2024, 11:09:14PM EDT

I'm going through the same metal debate I always go through when creating learning documentation. The traditional text-book format is broken. It always has been. That is why "recipe" books became so popular. Recipes are project-based, or more specifically, task based. Most all technical learning as to do with acquiring a specific skill associated with specific tasks. More general knowledge (contextual history, etc.) is less important. This is why "tutorials" (a horrible word) tend to dominate in popularity. Most people just want to know how to do a specific thing and only want to learn the prerequisites of doing that thing if they don't already know them. At the ultimate level, just wanting to get a job is a composition of wanting to know how to do a number of very specific things. Therefore, documenting universal, employable tech skills ultimately comes down to writing content and demonstrating how to fulfill the steps of a procedure to do a specific task. Hence my "programming humans" comparison. After all, what is a "tutorial" or "how to" if not code designed to program the person consuming it to be able to execute that procedure without error.

So how can we create a programming "language" for coding humans?

I think we can start with the highest-level procedural programming languages and pseudo-code for inspiration. Python comes to mind. The language will fundamentally have to be procedural even if event-driven because the implementation of an event handler is a series of steps, a procedure. It always comes down to specific tasks done in the scope of linear time—especially when dealing with human brains which are physically incapable of doing two things at the same time (consciously).

We can look at the headers of a learning module package and derive what it is about by the identifiers. Then, learners can drill into the body of their implementations to understand how the procedure is accomplished.

PACKAGE/VERB_TARGET_QUALIFIER(PARAMETERS)

We can also borrow the idea of abstract operational "interfaces" from Go, Java, and other languages. These outline the methods/functions that must be fulfilled but not *how* they are fulfilled. The natural language of fulfilling these interfaces might look something like the following:

```yaml
Interface:
  About:
    Name: Delete text
  Operations:
    - Delete current line
    - Delete N lines
    - Delete paragraph
    - Delete N paragraphs
```

The implementation of this interface might look something like the following:

```yaml
Procedure:
  About:
    Name: Delete current line
  Steps:
    - Enter command mode
    - Type dd
```

Anyone who knows Vim will realize immediately there are many methods that fulfill the `Delete current line` procedure even in Vim. None of them are wrong. All of them have to be accounted for in a full-set of procedural documents. But most could be eliminated when creating documentation/human programming when simplicity and best-practice is preferred. Indeed, most "tutorials" don't include all the possible methods to do a thing.

To further complicate matters, there's also an implied contextual qualifier here: "with Vim" but even that isn't precise enough because "with NeoVim" and "with Vi" are all identical. This becomes particularly relevant when creating learning content because being able to identify methods that specially work in several editors (but not others) is absolutely critical. Indeed, this is the reason so much argument boils up surrounding tool selection and disagreement. The ultimate question is which procedural operational interface does a given tool fulfill and whether its omissions or additions match the requirements of the problem at hand, in this case, accomplishing a work item as a software engineer or infrastructure SRE or hacker. Each one demands a different collection of otherwise identical interfaces.

The terminology is remarkably exact in its similarity between coding computers and programs in this case. A "method" is a specific implementation of procedural steps to fulfill an "operation" and in fact is derived from these terms in the greater context outside of a specific programming language. This is why confusing the terms "method" and "operation" is such a big and common mistake. An "operation" can be implemented by any number of different methods.

It's entertaining to realize that speaking these operations to a human or a computer assistant AI works equally well. When coming up with the text of the operation we can lean on the best practice of conversational user interfaces popularized by assistants and AIs that respond to natural language. Indeed, Amazon (Alexa) "actions" are exact sentences in the native language of the speaker. (By the way, this is why getopts needs to die as a command-line interface approach since removing it would automatically bridge the gap between programmed assistants, tools, and humans themselves, one human-computer and human-human interface specification to rule them all.)

Another essential element of these interfaces is stateful context. For example, "delete current line" assumes we are talking about "line of text" in the current "Delete text" abstract context. Context is fundamentally critical to sustainable interfaces that will survive progress into natural language input. Humans have used this for communication from the beginning and assistants driven by AI models are now doing the same thing. In fact, some of the most comical AI failures have been when the AI fails to imply the context wanted.

Let's also imaging this procedure is inside a file called `delete-current-line` inside a directory `vim` so that the path to it, when hosted on a unique web site would be something like `https://ocms.rwx.gg/vim/delete-current-line`.

This begs the question, where do we put the other procedures that fulfill this operation in Vim? In the same file? In a different file with a qualified name?

Another question is how much to put there? What if we don't want simplified documentation that only covers the one-best way? Do we break these out? What happens when we want a more advanced document later to program a human more deeply?

If you haven't notice yet, this is the fundamental problem with all documentation content on the Internet. No one to date has even attempted to organize documentation and human procedural programming in a manner that leverages the lessons learned from computer science itself.

