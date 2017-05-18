# Vim built-in completion

From insert mode:

## Completion

* `<c-x><c-o>` omnicompletion from your omnifunc in alphabetical order
* `<c-x><c-l>` whole line completion e.g. start at the beginning of a line, type a few chars from the beginning of another line, and hit the key combo. It will complete the entire other line!
* `<c-x><c-f>` file completion
* `<c-x><c-]` tag completion (useful when completing class names)
* `<c-n>` next match from document for word under cursor
* `<c-p>` previous match from document for word under the cursor

## Sort of meta-completion

* `<c-x><c-n>` expands the completion to include the next _word_.
* `<c-x><c-p>` expands the completion to include the previous _word_.

## Others

* `<c-x><c-k>` keywords in 'dictionary'
* `<c-x><c-t>` keywords in 'thesaurus', thesaurus-style
* `<c-x><c-i>` keywords in the current and included files
* `<c-x><c-d>` definitions or macros
* `<c-x><c-v>` Vim command-line
* `<c-x><c-u>` User defined completion
* `<c-x>s` Spelling suggestions

## Etc

* `<c-e>` Cancel completion
* `<c-y>` Accept the current completion
