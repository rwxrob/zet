# Use `{{json .}}` to Get JSON Schema from Go Template

It can be frustrating not knowing the data schema/model available when
using commands that take a Go template `--format` argument. One way to
just look at everything that is possible is to convert it to JSON first
with `{{json .}}` and pipe that through `jq`. Then, you can hone in on
what you want, or just use `jq` for everything.

This is particularly useful for `docker` which does not have an `-o
json` option as one may come to expect from using `kubectl` and family.
For example, the following prints out all the possible values for all
running containers:

```
docker ps --format '{{json .}}' | jq .
```

Which will produce something like the following:

```json
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:41:15 -0400 EDT",
  "ID": "1da31ee9eb8a",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "worker-3",
  "Networks": "k8s-workers",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "0B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:41:14 -0400 EDT",
  "ID": "d25e91e814b2",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "worker-2",
  "Networks": "k8s-workers",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "0B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:41:14 -0400 EDT",
  "ID": "a9e9a99f2a02",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "worker-1",
  "Networks": "k8s-workers",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "19B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:35:24 -0400 EDT",
  "ID": "51e4a8e191b8",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "control-3",
  "Networks": "k8s-control",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "0B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:35:24 -0400 EDT",
  "ID": "37be9f41eb0d",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "control-2",
  "Networks": "k8s-control",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "0B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
{
  "Command": "\"/bin/bash\"",
  "CreatedAt": "2021-10-15 14:35:23 -0400 EDT",
  "ID": "6acefac2e51a",
  "Image": "ubuntu",
  "Labels": "",
  "LocalVolumes": "0",
  "Mounts": "",
  "Names": "control-1",
  "Networks": "k8s-control",
  "Ports": "",
  "RunningFor": "9 hours ago",
  "Size": "24B (virtual 72.7MB)",
  "State": "running",
  "Status": "Up 9 hours"
}
```

Tags:

    #docker #json #golang #templates #tips
