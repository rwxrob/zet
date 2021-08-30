# RBAC and OPA (Gatekeeper) to Secure Kubernetes

When you are entering the Kubernetes building, RBAC is the security
person at the door checking badges (authorization). OPA Gatekeeper is
the person doing the full metal detector wand sweep (compliance).

Learning about the relationship between the Kubernetes RBAC resources
and the external OPA (Gatekeeper) resource (which might as well be
considered standard at this point since it is required for the CKS
certification and has been an industry standard for some time).

RBAC handles permissions for things. It this person in a specific group.
What's their role with regard to this namespace, to the entire cluster?

Gatekeeper covers how resources are deployed, the "policies" for how
they are deployed, changed, and managed over time. If this thing running
as root, has it set the proper constraints so it doesn't get out of
control, are all of it's ports locked down, is it using mTLS to
communicate, etc.

    #k8s #learning #security #devsecops #rbac #opa
