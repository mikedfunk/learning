# Regex Search

## Regular expressions in search

* `/[abc]` will search for `a`, `b`, or `c`
* `/^abc` will search for `abc123`, `abc456`, or `abc`
* `/\d` will search for `1`, `2565`
* not regex but `:%s/background/&-color` will replace all *background* with *background-color*

## Ranges

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

_(below is from http://vimregex.com/)_

Suppose you want to replace all occurrences of vi with VIM. This can be easily done with
```
s/vi/VIM/g
```
If you've tried this example then you, no doubt, noticed that VIM replaced all occurrences of vi even if it's a part of the word (e.g. navigator). If we want to be more specific and replace only whole words vi then we need to correct our pattern. We may rewrite it by putting spaces around vi:
```
s: vi : VIM :g
```
But it will still miss vi followed by the punctuation or at the end of the line/file. The right way is to put special word boundary symbols "\<" and "\>" around vi.
```
s:\<vi\>:VIM:g
```
