# Setup unit testing with Mocha and Chai

```sh
yarn add --dev mocha chai babel-core babel-preset-latest
```

then add this to your `.babelrc`:
```json
{
  "presets": [
    "latest"
  ]
}
```

put this in `./test/mocha.opts`:
```
--compilers js:babel-core/register
```

then create a test `./test/MyTest.js`:
```javascript
/* global describe, it */
import {expect} from 'chai'
describe('Feature: My Feature', () => {
  describe('Scenario: My Scenario', () => {
    it('greets', () => {
      expect(true).to.equal(true)
    })
  })
})
```

and run it:
```
mocha
```

you could also add it to your npm scripts. In `package.json`:
```json
{
  "scripts": {
    "test": "mocha"
  }
}
```

and run:
```
npm run test
```
