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
const add2 = x => x + 2
const four = add2(2)
const five = add2(3)
const six = add2(4)
```

#### Functions have input, logic, and output

Let's break down a function. First, we need input and logic.
```js
input => logic
```

Think of this as your `input` being handed over to the `logic` to be
evaluated. The `=>` shows your `input` where to go.


Now, assign the function to a name:

```js
const myFunction = input => logic
```

Now we have a fully declared function we can use, so let's use it!

```js
const output = myFunction(variables)
```

The above `myFunction(variables)` takes the `variables` as `input`, applies the
`logic`, then assigns the result to the `output`. This follows our programming
cycle of "input", "logic", "output" which you'll see repeated over and over
throughout your career. 


#### Two or More Arguments

A function with one argument:
```js
const addOne = x => x + 1
```

A function with two arguments:
```js
const add = (x, y)=> x + y
```

Notice the `()` and the `,`. When you have more than one argument, you need
to place them inside the `()` and separate them with commas. The `()` group
the arguments together so that JavaScript knows they're part of the same
function.

#### Functions Make Logic Reusable

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

And the following three usages:
```js
const four = subtract(7, 3)
const eight = multiply(2, 4)
const two = divide(4, 2)
```

#### Functions take in variables and output variables

So far, we've only used numbers for input, let's switch to a much more common
scenario of using variables:

```js
const add = (x, y)=> x + y

const one = 1
const two = 2
const three = 3

const four = add(one, three)
const five = add(two, three)
```

After `add(two, three)` is evaluated, `two` is still `2` and `three` is 
still `3`. The function simply takes the variables as inputs and outputs a
result.

#### Comparing Variables in Functions
Comparing things is the backbone of programming. Can this user access that information? Do we have pants in that color? Did you score enough to win the 
game?

```js
const isEqualTo5 = x => x == 5
const is4EqualTo5 = isEqualTo5(4)
const is5EqualTo5 = isEqualTo5(5)
```

A double equals `==` represents equality when comparing two values. Remember a
single `=` is an "assignment".

```js

const greaterThan5 = x => x > 5

const is6GreaterThan5 = greaterThan5(6)
const is4GreaterThan5 = greaterThan5(4)
```


