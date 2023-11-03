# MkDocs collaborative documentation PR editing

Primary use case: One editor with knowledge of MkDocs markdown edits the documentation live while other (potentially non-technical) stakeholders review and guide the edits in realtime (or near realtime). Optionally, the editor would share screen cast in realtime to show the content as it is edited, but the final render would only be required when those edits are commited and those commits pushed to the branch for the PR.

Requirements:

* Must be secure from snooping (no `mkdocs serve`, or with a tls proxy)
* Must be relatively performant at 500+ pages (`mkdocs serve --dirty`)
* Centralized vetting and control of container images used

Optional:

* TLS authenticated proxy main entry point

