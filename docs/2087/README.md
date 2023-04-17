# How to get requirements.txt PIP Python

Might be obvious to others, wasn't to me. Netlify, MkDocs, and lots of stuff uses the `requirements.txt` convention to add all the stuff a Python project needs, whether containerized or not.

```
pip install -r docs/requirements.txt
```

Add a `-U` if you want to get the latest of items that do not have a specified version.
