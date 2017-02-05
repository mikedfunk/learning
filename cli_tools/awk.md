# Awk

One way to use awk is to pipe a string to it, then break it into parts delimited by a string, then return parts of that string. E.g.:

```echo 'Yo hey' | awk -F' ' '{print $1}' <-- prints Yo```
```echo 'Yo hey' | awk -F' ' '{print $2 $2}' <-- prints hey Yo```
```echo 'Yo hey' | awk -F' ' '{print $1 "hithere" $2}' <-- prints Yo hithere hey```
