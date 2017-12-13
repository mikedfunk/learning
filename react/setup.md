# React Setup

## Requirements
```sh
npm install -g eslint
npm install -g ec
npm install -g babel-init
npm install -g poi
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

# set up babel
babel-init

# set up editorconfig
ec init

# now install some react dependencies, etc.
npm i -D babel-plugin-react-require react react-dom prettier-eslint
# and add "react-require" to the plugins in .babelrc

# keep it simple but flexible with poi
poi
```
