# NetRW

* You can use it like NERDTree's `<leader>nt` _(go to current file's directory in a left split)_ with `:Vex` then `P` to open the file in the previous split then `<c-w>o` to close all splits but the current one.
* `:Vex!` will open in a right split
* Same thing for `:Lex` to toggle vim's *project root directory* in a left split. Enter will open in the previous split and `:Le` again will close the file browser.
* `:Lex!` for a right split
* `v` will open in a vertical split
* `I` will toggle the top help bar
* `o` will open in a horizontal split
* `t` will open in a new tab
* `p` will preview the file
* `a` will cycle through visibility settings
* `D` will delete the current file/folder
* `%` will create a file
* `d` will create a directory
* `R` will rename a directory/file _(be sure to leave the / on the end if it's a directory)_
* `-` will go up one
* `<cr>` will expand/contract the current directory
* `<c-l>` reload the current directory
* `mf` mark a file
* `md` mark a directory
* `mt` set mark target directory
* `mc` copy marked files to marked target directory
* `mm` move marked files to marked target directory

[More stuff](https://gist.github.com/t-mart/610795fcf7998559ea80) or just `:help netrw`
