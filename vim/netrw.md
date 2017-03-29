# NetRW

* You can use it like NERDTree's `<leader>nt` _(go to current file's directory in a left split)_ with `:Vex` then `P` to open the file in the previous split then `<c-w>o` to close all splits but the current one.
* Or like NERDTree's `<c-e>` _(go to :pwd in left split)_: `:Le` to toggle browser open, hit enter to open in previous split, `:Le` to toggle browser closed. NOTE: if you change dirs in the split, you won't be able to toggle closed. :(
* Or stop trying to use the file browser split. Just `:e .` for pwd or `:e %:p:h` for current file dir, then enter over a file you want to open. No need to manage the split or deal with bugs if changing dirs.
* `:Vex!` will open in a right split
* `:Lex!` for a right split
* `v` will open in a vertical split
* `I` will toggle the top help bar
* `o` will open in a horizontal split
* `t` will open in a new tab
* `p` will preview the file
* `P` will opein in previous split
* `a` will cycle through visibility settings
* `D` will delete the current file/folder
* `%` will create a file
* `d` will create a directory
* `R` will rename a directory/file _(be sure to leave the / on the end if it's a directory)_
* `-` will go up one
* `<cr>` will expand/contract the current directory
* `<c-l>` reload the current directory

## Marking
You can mark files/dirs and do batch actions on them:
* `mf` mark a file
* `md` mark a directory
* `mt` set mark target directory
* `mc` copy marked files to marked target directory
* `mm` move marked files to marked target directory
* `mv` apply vim command to marked files (will prompt for command)
* `mx` apply shell command to marked files
* `mT` generate tags using marked files
* `mz` compress/decompress marked files
* `R` rename marked files
* `D` delete marked files
* `mb` append marked files to bookmarks
* `mB` delete marked files from bookmarks

[More stuff](https://gist.github.com/t-mart/610795fcf7998559ea80) or just `:help netrw`
