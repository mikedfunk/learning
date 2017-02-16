# Tmux Windows and Panes

Prefix is by default `<c-b>` but I change mine to `<c-a>`.

## Windows

* `<prefix> n` next window
* `<prefix> p` previous window
* `<prefix> {number}` go to {number} window
* `<prefix> . {number}` move the current window to number {number}
* `<prefix> c` create a new window
* `<prefix> &` kill window
* `<prefix> , {name}` rename window to {name}

## Panes

* `<prefix> "` create new horizontal split pane
* `<prefix> %` create new vertical
* `<prefix> x` kill pane
* `<prefix> <space>` cycle through pane arrangements
* `<prefix> <c-s-j>` increase pane size by 10 rows
* `<prefix> <c-s-k>` decrease pane size by 10 rows
* `<prefix> <c-s-h>` decrease pane size by 10 columns
* `<prefix> <c-s-l>` increase pane size by 10 columns
* `<prefix> z` toggle pane zoom
* `<prefix> r` rotate panes
* `<prefix> }` move pane right/down
* `<prefix> {` move pane left/up
* `<prefix> q` show pane numbers, type number to go to that pane

If you see a `*M` on the end of a pane, it's because that pane is "marked". You can unmark it with `<prefix> m`. [More info](http://superuser.com/questions/1056977/uppercase-m-at-the-right-of-window-name-in-tmux)
