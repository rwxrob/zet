# Use Dots in `kubectl explain` to Show Specifics

TIL that you can actually drill down with dotted notation to get more
useful information about a specific field using the `kubectl explain`
command. For example, `kubectl explain deployment.metadata.generation`
has the follow clarification which lets me sleep at night deleting it
when saving YAML from `kubectl get` commands.

```
KIND:     Deployment
VERSION:  apps/v1

FIELD:    generation <integer>

DESCRIPTION:
     A sequence number representing a specific generation of the desired state.
     Populated by the system. Read-only.
```

Tags:

    #k8s #kubectl #explain #tips
