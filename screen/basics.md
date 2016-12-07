# GNU Screen basics

[more detailed cheatsheet](http://aperiodic.net/screen/quick_reference)

## Sessions (screens)

* `screen -S mysessionname` create and attach to named session
* `screen -r` reattach to last session
* `screen -ls` show running sessions
* `screen -x mysessionname` attach to session by name
* `screen -d` detach session
* `screen -dAR mysessionname` detach any other screens attached to named session mysessionname and attach to it. create it if necessary.

## Windows

* `<prefix>"` list active windows, `k/j` for up/down, enter to select session
* `<prefix>A` rename current window
* `<prefix><prefix>` toggle between last window and current one

## Helpful ~/.screenrc settings

```
# remap to c-b
escape ^Bb
# always show the window bar in the footer
hardstatus on
hardstatus alwayslastline
hardstatus string "%w"
# ensure vim doesn't stay in the scrollback when exiting
altscreen on
# Enable mouse scrolling and scroll bar history scrolling
termcapinfo xterm* ti@:te@
```
