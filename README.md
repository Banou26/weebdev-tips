## Just use https://github.com/ryanmcdermott/clean-code-javascript instead lulz

## Contents
- [Tools](#tools)
  - [Babel](#babel)
- [Code](#code)
  - [Function naming](#function-naming)
  - [Parameters order](#parameters-order)
  - [Max parameters](#max-parameters)
  - [Boolean naming](#boolean-naming)

## Tools
### Babel
#### Use babel for browser compatibility and cool features
[Babel](https://babeljs.io/) allow you to use [ES](https://en.wikipedia.org/wiki/ECMAScript) features that aren't widely supported by [transpiling](https://en.wikipedia.org/wiki/Source-to-source_compiler) your code.

*It even allow you to use features that aren't yet standardised into [ES](https://en.wikipedia.org/wiki/ECMAScript), these are called proposals, this is pretty cool but be careful since your code could become invalid if you used a proposal that didn't get standardised or got their specs changed while being standardised*.

Babel also uses [core-js](https://github.com/zloirock/core-js) to [polyfill](https://en.wikipedia.org/wiki/Polyfill_(programming)) APIs that aren't widely supported either.

## Code

### Function naming
#### Try to name the function based on what it does
**Bad**
```js
const getData = async () => {
  const data = await fetch('https://example.com')
  computeData(data)
}
```
**Good**
```js
const getData = () =>
  fetch('https://example.com')

getData().then(computeData)
```
By naming your functions based on what they do, you convey a meaningful sense to them, you don't have to add a comment to explain what they do, it's explicit.

You also have less risks to wander off and make your function do things it shouldn't do, increasing it's complexity.

Doing this also makes your code more re-usable, by making it composable.

### Parameters order
#### Always put function arguments last
**Bad**
```js
const func = (callback, foo) => {}
```
**Good**
```js
const func = (foo, callback) => {}
```
Passing function arguments in last allow you to directly understand what is happening when calling this function.

One good example of this not applied is the ``setTimeout`` function, which first pass the function, and then the timeout argument, so if your function is 50lines long, you have to scroll down it all to finally be able to understand when it will actually be called.

### Max parameters
#### If a function has more than 3 arguments, put them into an object
**Bad**
```js
const func = (foo, bar, baz, qux, quux) => {}
```
**Good**
```js
const func = ({ foo, bar, baz, qux, quux }) => {}
```
This help futureproof your function, you can add or remove any number of parameters easily, without having to change all of the code that used this function.

You also don't need to remember the parameters order.

And this describe the parameters to the function called as you now have to use the arguments property names.

[ESLint rule](https://eslint.org/docs/rules/max-params)

### Boolean naming
#### Prepend the variable name of a boolean with 'is'
**Bad**
```js
const dog = true
const brown = false
```
**Good**
```js
const isDog = true
const isBrown = false
```

It's a simple change that reads much more naturally.
