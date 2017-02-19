# Cscope

[Cscope](cscope.sourceforge.net/cscope_vim_tutorial.html) lets you find usages of methods.

First you need to generate a cscope database:
```sh
find . -name *.php > cscope.files
cscope -b
```
This will generate `cscope.out` and `cscope.files`. You'll probably want to add those to your global gitignore.
Then within vim (if your vim is compiled with `+cscope`):
```
:cs add cscope.out
:cs find 0 myMethodName
```
