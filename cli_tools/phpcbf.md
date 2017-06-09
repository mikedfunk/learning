# PHPCBF

[php coding beautifier and fixer](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically)

phpcbf uses your `phpcs.xml` to fix fixable errors. Just do 
```phpcbf --standard=phpcs.xml```
You can do a dry run by just running `phpcs`.

You can also use phpcbf as a vim formatprg and automatically format on save:
```viml
autocmd FileType php set formatprg=phpcbf\ --standard=phpunit.xml
autocmd BufWritePre *.php :normal gggqG
autocmd BufWritePre *.php exe "normal! gggqG\<C-o>\<C-o>"
```
