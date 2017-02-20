# Mocking with Sinon

Example mocha test:
```javascript
/* global it */
import sinon from 'sinon'
import {expect} from 'chai'
import Person from '../Person'
import Head from '../Head'
import Arm from '../Arm'

it('greets - stub', () => {
  let sandbox = sinon.sandbox.create()
  sandbox.stub(Head.prototype, 'nod', () => 'nods')
  sandbox.stub(Arm.prototype, 'wave', () => 'waves')
  const head = new Head()
  const arm = new Arm()
  const person = new Person(head, arm)
  expect(person.greet()).to.equal('nods, waves')
  sandbox.restore()
})

it('greets - mock', () => {
  let sandbox = sinon.sandbox.create()
  sandbox.mock(Head.prototype).expects('nod').once()
  sandbox.mock(Arm.prototype).expects('wave').once()
  const head = new Head()
  const arm = new Arm()
  const person = new Person(head, arm)
  expect(person.greet()).to.equal(', ')
  sandbox.restore()
})

it('greets - stub instance', () => {
  // another way: this is not as useful but shows it automatically stubs all
  // methods to return nothing
  const head = sinon.createStubInstance(Head)
  const arm = sinon.createStubInstance(Arm)
  const person = new Person(head, arm)
  expect(person.greet()).to.equal(', ')
})

it('greets - spy', () => {
  let sandbox = sinon.sandbox.create()
  sandbox.spy(Head.prototype, 'nod')
  sandbox.spy(Arm.prototype, 'wave')
  const head = new Head()
  const arm = new Arm()
  const person = new Person(head, arm)
  person.greet()
  expect(arm.wave.called)
  expect(head.nod.called)
  sandbox.restore()
})
```
