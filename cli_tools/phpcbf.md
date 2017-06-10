# PHPCBF

[php coding beautifier and fixer](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically)

Alternatives: [php-cs-fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer), [PHP_Beautifier](https://github.com/clbustos/PHP_Beautifier)

phpcbf uses your `phpcs.xml` to fix fixable errors. Just do 
```sh
phpcbf --standard=phpcs.xml --extensions=php .
```
Strangely it also tries to format js, css, etc. if you don't specify only php :/

You can do a dry run by just running `phpcs` instead.

You can also use phpcbf as a vim formatprg and automatically format on save:
```viml
autocmd FileType php set formatprg=phpcbf\ --standard=phpunit.xml
autocmd BufWritePre *.php :normal gggqG
autocmd BufWritePre *.php exe "normal! gggqG\<C-o>\<C-o>"
```
