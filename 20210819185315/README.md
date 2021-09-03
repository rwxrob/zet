# Istio Fucks Up `kubectl run`, Forever

I'm really growing to hate Istio and I'm still very new to all this.
I know. I know. Istio saves the day and is the "network stack" for Cloud
Native, blah, blah. I still fucking hate it.

I hate the hubris behind the idiotic decision the Istio team continues
to stand behind by destroying the `run` command (and stuff similar to
it) with sidecar injection. If you run Istio in your cluster you might
as well make an alias for `run` that says, "Sorry, Istio ruined me."

You can read all about this shit-storm of failure on the `istio/istio`
project issue number 11130. 

How the fuck did the Istio team think all of this was okay to begin
with? Did someone say, "Let's fuck up one of the most commonly used
`kubectl` commands for everyone for the rest of eternity?" Sure feels
like it based on the response in that thread. No one seems to even give
a shit from the Istio team. Either that, or they are pretending to
ignore that stupidity as if never happened, typical of certain
types of tech people. "There is no usability bug. You can go about your
business. \*waves Jedi hand\*" I *hate* that shit about people in our
industry.

The problem stems from `run` not supporting the `--container` option to
indicate the container you want (like `exec` supports). I'm sure
everyone out there thinks wanting to use `run` is something only
juvenile noobs want to use, but that thread confirms there are a ton of
other reasons to want it.

The only solution is to turn it off, but often it is exactly Istio and
networking stuff that you need to debug with a `run`. Sure you can do
the same in a much more convoluted way, but it just sucks that you have
to do it. Here's how to disable it:

```bash
#!/bin/bash

overrides='
{
  "metadata": {
    "annotations": {
      "sidecar.istio.io/inject": "false"
    }
  }
}
'

exec kubectl run netshoot --rm -it \
  --image nicolaka/netshoot:latest \
  --namespace "${1:-$(ns)}" \
  --overrides "$overrides" \
  -- /bin/bash

```

See also:

* <https://github.com/istio/istio/issues/11130>

    #istio #k8s #cloud #fail #kubectl #bugs
