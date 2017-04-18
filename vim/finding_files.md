# Finding files

## Open using glob patterns

You don't need netrw to find and open a file. You can do:
```
:e **/PartOfFileName<tab>
```
and you'll get the first match. If that's not the one you need, `<c-n>` and `<c-p>` will navigate to other matches.

## Using :find

You can also use `:find PartOfFileName<tab>` to open a file. Tab will continue to find other matches. Enter to open the file. For this to work for all files, you'll need to do `set path+=**` in your `.vimrc`. This allows you to search recursively through your entire vim pwd folder.

These use glob args, which work like this:

* `*` Matches any string, of any length
* `foo*` Matches any string beginning with foo
* `*x*` Matches any string containing an x (beginning, middle or end)
* `*.tar.gz` Matches any string ending with .tar.gz
* `*.[ch]` Matches any string ending with .c or .h
* `foo?` Matches foot or foo$ but not fools


## Opening multiple matches

```
:args **/PartOfFileName
:next <-- go to next result, or...
:previous
:first
:last
]a <-- vim-unimpaired
```

## Searching for matching ctags

You can also search for file (and matching line) by ctag:
```
:tselect PartOfTagName
```
You'll get a list of matches. Hit the matching number to jump there. If you want to jump the first match if one is found, use:
```
:tjump PartOfTagName
```
