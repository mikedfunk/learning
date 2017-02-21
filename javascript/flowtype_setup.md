#Flowtype setup

Without all the bullshit.

```sh
yarn add --dev flow
yarn add --dev flow-bin
yarn add --dev flow-typed
yarn add --dev babel-plugin-transform-flow-strip-types
```

`flow init` and add this to your `.flowconfig`:
```dosini
[ignore]
.*/node_modules/fbjs/.*
.*/git/.*
```

set up [flow typed](https://github.com/flowtype/flow-typed/#huh):
```
./node_modules/.bin/flow-typed intstall
```

add this to your `.babelrc`:
```json
{
  "plugins": ["transform-flow-strip-types"]
}
```

## OPTIONAL configure syntastic to use flow

in your `.vimrc` provided you have [syntastic](https://github.com/vim-syntastic/syntastic) installed:
```vim
if executable('flow') | call add(g:syntastic_javascript_checkers, 'flow') | endif
```

## OPTIONAL eslint config - the easy way

This won't actually check flow but it will allow flow syntax without freaking out. In this example I use syntastic above to actually check flow stuff.

if using [standard](https://standardjs.com) just install [an eslint config](https://www.npmjs.com/package/eslint-config-standard-flow):
```sh
yarn add --dev eslint-config-standard
yarn add --dev eslint-config-standard-flow
```
and add it to your `extends` in your `.eslintrc.json`:
```json
{
  "extends": ["standard", "standard-flow"]
}
```

## OPTIONAL eslint config - the hard way through babel

Added benefit - eslint itself actually checks for flow errors, so no need for another checker. This is not needed if you're just going by an eslint config because the eslint config abstracts `eslint-plugin-flowtype` to turn rules on and off.

```sh
yarn add --dev eslint
yarn add --dev babel-eslint
yarn add --dev eslint-plugin-flowtype
yarn add --dev eslint-plugin-flowtype-errors
```

`eslint --init`, then add this to your `.eslintrc.json` (merge with json):
```json
{
  "extends": [
    "plugin:flowtype/recommended"
  ],
  "parser": "babel-eslint",
  "plugins": [
    "flowtype",
    "flowtype-errors"
  ],
  "rules": {
  },
  "settings": {
    "flowtype": {
      "onlyFilesWithFlowAnnotation": true
    }
  }
}
```

You can adjust flow rules with either method (easy or hard) - see the [docs for this plugin](https://github.com/gajus/eslint-plugin-flowtype).

-----

## But what the hell does this do?

* [flowtype](https://flowtype.org/) adds typing, interfaces, and static type checking to javascript
* this eslint plugin makes eslint go through babel, then adds a flowtype babel plugin.
* the strip types package de-flowtypes your code. Not sure what it does about interfaces and stuff...

## What's the difference between `eslint-plugin-flowtype` and `eslint-plugin-flowtype-errors`?

* [eslint-plugin-flowtype](https://www.npmjs.com/package/eslint-plugin-flowtype) provides some additional linting rules for flowtype that you can turn off/on. It's usually used by a eslint config like [eslint-config-standard-flow](https://www.npmjs.com/package/eslint-config-standard-flow), and individual rules are toggled in the packaged eslint config. It does not do anything with `flow-bin`.
* [eslint-plugin-flowtype-errors](https://www.npmjs.com/package/eslint-plugin-flowtype-errors) actually displays flowtype errors through eslint. It checks errors in `flow-bin`. It's not necessary if you just add flow as a checker in syntastic or use the flow plugin in sublime.
