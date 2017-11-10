# Tags

Vim has integration with ctags. You can generate tags for your project by running `:!ctags -R` in the project root. Ctags isn't maintained, so it's recommended to instead use [universal ctags](https://github.com/universal-ctags/ctags). Tag shortcuts:

* `<c-]>` jump to tag definition for word under cursor
* `<c-t>` jump back in the tag stack (go back after jumping to tag)
* `<c-w> }` open the tag definition under cursor in a preview window (`<c-w> z` to close preview when done)
* `<c-w> ]` jump to tag definition in a horizontal split
* `:tag myTag` open tag definition for `myTag` in current window. Goes to first match.
* `:tag /myTag` fuzzy search for `myTag`. You can also do regex searches like `:tag /^myTag`
* `:tags` show the current tag navigation stack
* `:ts[elect] myTag` shows all tags for `myTag`, asking you to choose the one you want. Doesn't fuzzy search unfortunately, only exact matches. BUT you can fuzzy search with `:tselect /PartOfTag`
* `:sts[elect] myTag` same as above but splits window when tag is selected
* `Vtselect` command:

```vim
" like stselect but for vertical split e.g. :Vtselect /MyPartialTag
command! -nargs=1 Vtselect vsp | exec 'tselect ' . <f-args>
```

* `g]` like `<c-]>` but use tselect instead of tag
* `:tj[ump] myTag` like tselect but jumps to it if only one match.
* `:stj myTag` ... in a split
