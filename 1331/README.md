# Generate an Elliptical Curve 25519 GPG Key Pair

```
gpg --full-generate-key --expert
```

Select "ECC, ECC" and then "Curve 25519".

Then export it and save it in an encrypted store of some kind for safe
keeping:

```
gpg --export-secret-keys --armor
```
