# Watch
```sh
yarn global add watch
```
Now you can watch directories for changes and take action in response like this:
```sh
watch "clear; ./vendor/bin/phpunit --colors" src tests
```

there's also the builtin linux [watch](https://linux.die.net/man/1/watch) command, which is different. By default it just runs a command every 2 seconds. like `watch mycommand`. You can also use it with piped commands like so: `watch 'ps -ef | grep something'`
