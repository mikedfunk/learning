# Composer Local Repositories

If you're working on a task that depends on a pull request you have out, or you're working on something that depends on a [composer](http://getcomposeer.org) package that's not published on [packagist](http://packagist.org) yet, you can just set it up temporarily as a local dependency instead. In composer.json:

```json
{
    "repositories": [
        {
            "type": "path",
            "url": "../../packages/my-package"
        }
    ],
    "require": {
        "my/package": "*"
    }
}
```

Much easier than swapping symlinks on composer update/install. No need to point it to an unpublished fork instead.
