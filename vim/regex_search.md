# Regex Search

## Regular expressions in search

* `/[abc]` will search for `a`, `b`, or `c`

## ranges

* `:10,20s/replaceme/new/g` replace `replaceme` with `new` on lines 10-20

## Search and Replace

```
:%s/abc/123/cgil
```

Here is what the `cgil` does:

* `c` will ask to confirm every replacement with a `y` or `n`
* `g` will replace all matches on a line, not just the first one
* `i` will ignore case
* `l` will respect case. Of course you don't want to use `i` and `l` together.
