## Contents
- [Function](#function)
  - [Max parameters](#max-parameters)

## Function
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
