## Contents
- [Tools](#tools)
  - [Babel](#babel)
- [Function](#function)
  - [Name](#name)
  - [Max parameters](#max-parameters)

## Tools
### Babel
#### Use babel for browser compatibility and cool features
[Babel](https://babeljs.io/) allow you to use [ES](https://en.wikipedia.org/wiki/ECMAScript) features that aren't widely supported by [transpiling](https://en.wikipedia.org/wiki/Source-to-source_compiler) your code.

*It even allow you to use features that aren't yet standardised into [ES](https://en.wikipedia.org/wiki/ECMAScript), these are called proposals, this is pretty cool but be careful since your code could become invalid if you used a proposal that didn't get standardised or got their specs changed while being standardised*.

Babel also uses [core-js](https://github.com/zloirock/core-js) to [polyfill](https://en.wikipedia.org/wiki/Polyfill_(programming)) APIs that aren't widely supported either.

## Function
### Name
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
