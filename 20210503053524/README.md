# Adjust Offset Date/Time Easily

I didn't learn till wait later in life that the `-d` option to `date`
allows for a rather powerful domain-specific language for creating an
offset to the actual date displayed.

```
secs=$(date -d '2021-01-19T05:52:43-05:00 +1 minute' +%s)
echo $secs
```
