## Function arguments

### If a function has more than 3 arguments, put them into an object
**Bad**
```js
const func = (foo, bar, baz, qux, quux) => {}
```
**Good**
```js
const func = ({ foo, bar, baz, qux, quux }) => {}
```
This help futureproof your function, you can add or remove any number of parameters easily.

You also don't need to remember the parameters order.

And this describe the parameters to the function called as you now have to use the arguments property names.
