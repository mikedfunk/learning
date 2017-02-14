## php-cs-fixer config

in `.php_cs`:
```
<?php

$finder = PhpCsFixer\Finder::create()
    ->exclude('somedir')
    ->notPath('src/Symfony/Component/Translation/Tests/fixtures/resources.php')
    ->in(__DIR__)
;

return PhpCsFixer\Config::create()
    ->setRules(array(
        '@PSR2' => true,
        'strict_param' => true,
        'array_syntax' => array('syntax' => 'short'),
    ))
    ->setFinder($finder)
;
NOTE: exclude will work only for directories, so if you need to exclude file, try notPath.

See [Symfony\Finder](http://symfony.com/doc/current/components/finder.html) online documentation for other Finder methods.
