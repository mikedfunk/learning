# React Setup

## Requirements
```sh
npm install -g eslint
npm install -g ec
npm install -g babel-init
npm install -g poi
npm install -g flow-bin
npm install -g flow-typed
(vim with ale)
```

## Vim
```vimscript
let g:ale_linters = { 'javascript': ['eslint', 'flow'] }
let g:ale_fixers = { 'javascript': ['prettier_eslint'] }
```

## Shell
```sh
# setup eslint
eslint --init

# make package.json
npm init -y

# starting point for flow config if you want
flow init

# All you have to do when you add one or more new dependencies to your project is run flow-typed install. This will search the libdef repo and download all the libdefs that are relevant for your project and install them for you. After that, simply check them in and be on your way!
# https://github.com/flowtype/flow-typed
flow-typed install

# set up babel
babel-init

# set up editorconfig
ec init

# now install some react dependencies, etc.
npm i -D babel-plugin-react-require react react-dom prettier-eslint
# and add "react-require" to the plugins in .babelrc

# keep it simple but flexible with poi
# https://egghead.io/courses/make-webpack-easy-with-poi
# https://poi.js.org
poi
```
