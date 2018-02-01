# Show Function Signature

There are two builtin ways to display a function signature for a function defined in userland:
* `[i` will show the function signature under the cursor in the command line. see `:help include-search`
* `<c-w>}` will open the function signature area in a preview window. `<c-w>Z` to close it.

There's also plugins. I use [echodoc](https://github.com/Shougo/echodoc.vim) to display function signatures from completions in the command line. What's cool about this is that it highlights which param you're in as you go. Downside is you have to trigger completion and accept with <c-y> to make the echodoc show up.
