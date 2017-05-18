# Go to variable definition

* `gd` will take you to the local declaration.
* `gD` will take you to the global declaration.
* `g*` search for the word under the cursor (like `*`, but `g*` on 'rain' will find words like 'rainbow').
* `g#` same as `g*` but in backward direction.
* `ctrl-w i` will go to definition in a horizontal split
* `[I` will show all usages of the current word in the document from the top with line numbers
* `]I` like `[I` but starting at the current line
* `[ ctrl-I` go to first usage of current word in file without searching it. `gd` highlights `hlsearch` matches which is annoying when you don't want it. This does not.
* `] ctrl-I` like `[ ctrl-I` but from the current line

## Other go to stuff

* `gn` will go to and select the next search result
* `gN` will go to and select the previous search result
