## Contents
- [Function](#function)
  - [Name](#name)
  - [Max parameters](#max-parameters)

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
