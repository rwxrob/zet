# Bash `select` When You Can

A lot of people don't know you can use `select` to easily create a
select menu with user prompt:

```bash
select file in $(ls -1 ~/Documents); do 
  echo "$file"
  # do something with $file;
done
```
