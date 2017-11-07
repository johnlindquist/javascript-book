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

#### Functions have input, logic, and output

Look at the following arrow function
```js
()=>
```

All by itself, it doesn't do anything. So let's add some input and logic.
```js
(input)=> logic
```

So your input will be named inside the `()` (these are called `arguments` or 
`args`) then the logic will happen on the right side of the `=>`. Now, let's 
assign the function to a name:

```js
const myFunction = (input)=> logic
```

Now we have a fully declared function we can use, so let's use it!

```js
const output = myFunction(variables)
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

After `add(two, three)` is evaluted, `two` is still `2` and `three` is 
still `3`. The function simply takes the variables as inputs and outputs a
result.