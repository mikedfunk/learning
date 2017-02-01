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
