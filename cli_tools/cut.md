# Cut

You can pipe stuff to the `cut` command like so:

```
echo 5.6.7 | cut -d. -f1
# ^ returns 5
echo 5.6.7 | cut -d. -f2
# ^ returns 6
```
