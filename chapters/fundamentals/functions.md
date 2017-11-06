## Functions

Let's take our variable example and move the logic into a function


*Before*
```js
const four = 2 + 2
const five = 2 + 3
const six = 2 + 4
```

*After*
```js
const add = (x, y)=> x + y
const four = add(2, 2)
const five = add(2, 3)
const six = add(2, 4)
```

#### A function makes logic reusable

Take a look at the following three functions
```js
const subtract = (x, y)=> x - y
const multiply = (x, y)=> x * y
const divide = (x, y)=> x / y
```

The function on the right is assigned to a name on the left which describes
exactly what the function does. In fact, all throughout your career, one of
the biggest challenges you'll face isn't necessarily writing the function, but
_naming_ the function so that anyone who uses it knows exactly what the function
should be used for!

#### Functions have inputs and outputs, they shouldn't re-assign variables
```js
const add = (x, y)=> x + y
const two = 2
const three = 3
const five = add(two, three)
```

Above, after `add(two, three)` is evaluted, `two` is still `2` and `three` is 
still `3`. The function simply takes the variables as inputs and outputs a
result.