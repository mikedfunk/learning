# Lazy Regex Until Character

Let's say you want to get this string:
```
segment1/segment2
```
from this url:
```
http://whatever.com/segment1/segment2?query=thing/thing
```

You can do that with this regex:
```
/^\/?(.[^?]*).*$/
```

The important part is `[^?]`. This means match any character except `?`. Then continue on. It's another way to do lazy matching. I found this out because `(.*?)\??.*$` was not working because it was too lazy. It only matched the first character before the question mark (`s`).
