# Glamour considers block quotes long sentences

Just got another solid reason to throw out block quotes other than single paragraphs out in KEGML. It would seem the makers of Glamour agree. Glamour renders all paragraphs in a block quote together into a single sentence (without even a space after the last period of the previous paragraph).

```md
> "It is possible that answers.microsoft.com may not work with text-based browsers such as lynx or w3m because these browsers do not support modern web technologies and may not be able to properly render the website's content.
>
> Text-based browsers are designed to display simple, text-based content and may not be able to handle more complex web pages that rely on advanced features such as JavaScript, CSS, and multimedia content. As a result, websites that use these technologies may not be fully accessible or may not display correctly when viewed with a text-based browser."

And I just couldn't resist:

> The bug is that Microsoft has decided to go directly against the council of Tim Berners-Lee and other Web leaders by making their documentation site depend completely on a technology that prevents researchers and the blind from reading it when there was no direct need for such a "modern" dependency.
>
> For the record, there are 10s of thousands of companies and sites that do. Microsoft just doesn't. This sends a very clear message to the world. I've already made sure that thousands have read this, and will continue to do so. People need to know.

```

Turns into this monstrosity:

```
│ "It is possible that answers.microsoft.com may not work with text-based browsers such as lynx or w3m because these browsers do not support modern web technologies and may not be able to properly render the website's content.Text-based browsers are designed to display simple, text-based content and may not be able to handle more complex web pages that rely on advanced features such as JavaScript, CSS, and multimedia content. As a result, websites that use these technologies may not be fully accessible or may not display correctly when viewed with a text-based browser."

And I just couldn't resist:

│ The bug is that Microsoft has decided to go directly against the council of Tim Berners-Lee and other Web leaders by making their documentation site depend completely on a technology that prevents researchers and the blind from reading it when there was no direct need for such a "modern" dependency.For the record, there are 10s of thousands of companies and sites that do. Microsoft just doesn't. This sends a very clear message to the world. I've already made sure that thousands have read this, and will continue to do so. People need to know.
```
