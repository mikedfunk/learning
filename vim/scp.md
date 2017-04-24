# Editing files on remote servers over scp

Easiest way is just to
```
:e scp://my-server-name//root/path/to/my/file.txt
```
Or just `vim` in front if you're opening a new instance.
When you save it is uploaded back. You could also use `:Nread` but you would have to `:Nwrite` with the same scp:// path.
