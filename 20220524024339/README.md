# Home OpenLDAP/OIDC Provider

One of the most critical components of any IT infrastructure is a method
of authentication and authorization for different applications. OpenLDAP
is a standard for authentication used for decades. OpenID, or OIDC, is a
method of authorization used prevalently for about a decade at this
point. Understanding how to set both of them up and use them to
authenticate an application consistently is a core skill for any
infrastructure engineer. Unfortunately, I the last time I did OpenLDAP
was in the 90s way before OIDC even though I've written the `klogin`
that uses OIDC at work currently and my own `auth-go` for doing
three-legged OAuth sessions. But I really need to go through the entire
process of setting both of them up on my home lab, no Terraform, no
Ansible, just a VM running both that I can migrate later.
