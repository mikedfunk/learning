# ES6 dependency injection setup

assuming you have [babel](babeljs.io) set up already:
```sh
yarn add --dev dependency-injection-es6 
yarn add --dev babel-plugin-transform-decorators-legacy
```

Add this to your `.babelrc`:
```json
{
  "plugins": [
    "transform-decorators-legacy"
  ]
}
```

If you use [flowtype](http://flowtype.org), add this to your `.flowconfig`:
```dosini
[options]
esproposal.decorators=ignore
```

Set your es6 class to inject dependencies. E.g. in `Person.js`:
```javascript
import {inject} from 'dependency-injection-es6'
class Arm {
  wave () {
    return 'waves'
  }
}

class Head {
  nod () {
    return 'nods'
  }
}

@inject(Head, Arm)
class Person {
  constructor (head, arm) {
    this.head = head
    this.arm = arm
  }
  greet () {
    return [this.head.nod(), this.arm.wave()].join(', ')
  }
}
export {Arm, Head, Person}
```

Then resolve the top level with the service container. E.g. in `app.js`:
```javascript
import {container} from 'dependency-injection-es6'
import {Person, Arm, Head} from './Person'

let person: Person = container.getInstanceOf(Person)
console.log(person.greet())
```

* for testing see [mocha setup](javascript/mocha_setup.md)
* for mocking see [sinon](javascript/sinon.md)
