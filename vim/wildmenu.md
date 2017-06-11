# Wildmenu

Vim has a cool feature to complete commands, files, directories, functions, etc. in command mode. Just do this if you haven't already:

```
set wildmenu
set wildmode=full
```

Then do this:
```
:e <tab>
```

You'll get a cool horizontal completion menu. tab or shift-tab through it. if over a directory, press down to open it, up to go up a directory.
