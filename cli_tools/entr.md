# Entr

Watches for file changes and takes an action. Useful for listening and running unit tests.

Install:
```
brew install entr
```

Example:
```sh
# noglob is for zsh
noglob ls src/**/*.php tests/**/*.php | entr -c phpunit --colors 
```

[docs](http://entrproject.org/)

Alternatives:
* [watchr](https://github.com/mynyml/watchr) (ruby gem)
* [chokidar](https://www.npmjs.com/package/chokidar-cli) (no color output)
