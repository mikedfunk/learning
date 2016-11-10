# Populate replace dialog

You can populate the vim replace command (or any command) with data from other places, e.g.

```
:s/|<-- cursor here: press <c-r><c-w> for the word under the cursor or <c-r><c-a> for the WORD under the cursor
```

Pneumonic: it's the opposite of `<c-w><c-r>` to rotate windows

## Other `<c-r>` stuff (from insert mode)

* `<c-r>/` insert the last search string at the cursor
* `<c-r>*` insert clipboard comments
* `<c-r>:` insert last command-line
* `<c-r>%` insert the current file name
* `<c-r>.` insert the last inserted text
