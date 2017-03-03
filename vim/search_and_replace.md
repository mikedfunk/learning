# Search and Replace

You could do this with `sed`, but here's a vim way to do this:

```
:args **/*MyFuzzyFileMatch* <-- matches entire path so /dir/MyFuzzleFileMatch/MyFile.txt would also match
:argdo %s/replaceme/NEW_TEXT/gc <-- replace and confirm each one
```

If you don't want to confirm each one:
```
:set hidden
:args **/*MyFuzzyFileMatch* <-- matches entire path so /dir/MyFuzzleFileMatch/MyFile.txt would also match
:argdo %s/replaceme/NEW_TEXT/g <-- replace without confirm
:argdo update
```

Also screw all of this - Vim 7.3 now has `cdo` to operate on files in quickfix:
```
:grep myterm
:cdo s/myterm/newterm/gc | update
```
