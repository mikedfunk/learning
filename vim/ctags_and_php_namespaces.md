# Universal Ctags and php namespaces

* To generate a tags file that utilizes modern php features, don't use vanilla *ctags*. Instead use [univeral ctags](https://github.com/universal-ctags/ctags).
* When generating tags, first put this in `~/.ctags`:

```
# vim: set foldmethod=marker:
# see https://github.com/shawncplus/phpcomplete.vim/wiki/Getting-better-tags
# Basic options {{{
--recurse=yes
--tag-relative=yes
--sort=foldcase
--fields=+aimlS
# fixes double backslash in namespaces
--output-format=etags
# }}}

# additional excludes {{{
--exclude=.git
--exclude=bootstrap.php.cache
--exclude=classes.php.cache
--exclude=app/cache
--exclude=__TwigTemplate_*
# }}}

# language-specific {{{
--languages=php,ruby
--PHP-kinds=cfnit
--regex-ruby=/(^|;)[ \t]*(class|module)[ \t]+([A-Z][[:alnum:]_]+(::[A-Z][[:alnum:]_]+)+)/\3/c,class,constant/
# }}}
```

If you don't limit the languages it will try to index coffeescript, javascript, css, etc. The *output format* Is the key part here - it indexes php namespaces correctly as `\My\Namespace` instead of `\\My\\Namespace`. [more info](https://github.com/universal-ctags/ctags/issues/815)
