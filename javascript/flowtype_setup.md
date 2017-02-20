#Flowtype setup

Without all the bullshit.

```sh
yarn add --dev flow
yarn add --dev flow-bin
yarn add --dev babel-plugin-transform-flow-strip-types
```

`flow init` and add this to your `.flowconfig`:
```dosini
[ignore]
.*/node_modules/fbjs/.*
.*/git/.*
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

Added benefit - eslint itself actually checks for flow errors, so no need for another checker

```sh
yarn add --dev eslint
yarn add --dev babel-eslint
yarn add --dev eslint-plugin-flowtype
```

`eslint --init`, then add this to your `.eslintrc.json` (merge with json):
```json
{
  "extends": [
    "plugin:flowtype/recommended"
  ],
  "parser": "babel-eslint",
  "plugins": [
    "flowtype"
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

You can adjust flow rules - see the [docs for this plugin](https://github.com/gajus/eslint-plugin-flowtype).

-----

## But what the hell does this do?

* [flowtype](https://flowtype.org/) adds typing, interfaces, and static type checking to javascript
* this eslint plugin makes eslint go through babel, then adds a flowtype babel plugin.
* the strip types package de-flowtypes your code. Not sure what it does about interfaces and stuff...
