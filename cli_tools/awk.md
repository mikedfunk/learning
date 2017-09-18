# Awk

One way to use awk is to pipe a string to it, then break it into parts delimited by a string, then return parts of that string. E.g.:

```sh
echo 'Yo hey' | awk '{print $1}' # <-- prints Yo
echo 'Yo hey' | awk -F' ' '{print $1}' # <-- prints Yo
echo 'Yo hey' | awk '{print $2 $1}' # <-- prints hey Yo
echo 'Yo hey' | awk '{print $1 "hithere" $2}' # <-- prints Yo hithere hey
```

[more](http://blog.jpalardy.com/posts/awk-tutorial-part-1/)
