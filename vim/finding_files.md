# Finding files

You don't need netrw to find and open a file. You can do:
```
:e **/PartOfFileName<tab>
```
and you'll get the first match. If that's not the one you need, `<c-n>` and `<c-p>` will navigate to other matches.

You can also use `:find PartOfFileName<tab>` to open a file. With wildmenu enabled, tab will continue to find other matches. Enter to open the file. For this to work for all files, you'll need to do `set path+=**` in your `.vimrc`. This allows you to search recursively through your entire vim pwd folder. Or you can just `:find **/PartOfFileName<tab>`.

## Opening multiple matches

```
:args **/PartOfFileName
:next <-- go to next result, or...
:previous
:first
:last
]a <-- vim-unimpaired
```
