## Mocking require and import in testing with proxyquire

Want to swap out mocks, spies, or stubs for js dependencies in testing? Of course you do! And it's _sooo_ easy. You don't have to change *any* of your code! No service container code in your modules, no decorators, no string service container definitions to resolve, just `import` or `require` like it was before! Downside is it's not a real di container. You can't set project-wide mappings. It's just for swapping require in testing. But it's so little effort for such a helpful element of the usual DI! 

This is the coolest thing ever:
```sh
yarn add --dev mocha chai proxyquire babel-core babel-preset-latest
```

and add this in `test/mocha.opts`:
```
--compilers js:babel-core/register
```

Here's a sample test:
```javascript
/* global it */
import {expect} from 'chai'
import proxyquire from 'proxyquire'
it('tests', () => {
  const armStub = { wave () { return 'I wave' } }
  const headStub = { nod () { return 'I nod' } }
  // Person has `import Arm from '../Arm' and same for head.
  const Person = proxyquire('../Person', { '../Arm': armStub, './Head': headStub }).default
  const person = new Person(armStub, headStub)
  expect(person.greet()).to.equal('I wave, I nod')
})
```

*THAT'S IT! NO DECORATORS! NO FANCY STUFF!* So easy to write tests with this! AAAAAAAH
