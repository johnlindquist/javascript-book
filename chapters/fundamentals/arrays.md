# Arrays

More often than not, you'll be working with a collection of data: Users
of an app, posts on a blog, timestamps on a video, or any group of related
types that all belong together. This is where arrays come in:

```js
const numbers = [1, 2, 3]
const people = ["Kim Wilkes", "John Lindquist", "Mindy Lindquist"]
```

> Use `[]` to declare an Array

Notice how the numbers and names are grouped together inside of `[]`
and separated by commas.

Arrays can hold any type of variable:

```js
const one = 1
const two = 2
const three = 3
const myNumbers = [one, two, three]
```


#### Filter Out Values

Every Array has a `.filter()` method on it, so let's use our `greaterThan5`
function we declared earlier:

```js
const greaterThan5 = x => x > 5

const myNumbers = [1,2,3,4,5,6,7,8,9]
const myNumbersGreaterThan5 = myNumbers.filter(greaterThan5)
//myNumbersGreatThan5 is now assigned to [6,7,8,9]
```

We've used our `greaterThan5` function to match every number in the `myNumbers`
Array that's greater than 5 and give us back a new Array.


#### `startsWith`, `includes`, and `endsWith`
JavaScript comes with some handy methods we can use with strings to compare
them against other strings:

```js
const johnStartsWithJ = "John".startsWith("J")
//true
const wilkesIncludesIlk = "Wilkes".includes("ilk")
//true
const kimEndsWithIm = "Kim".endsWith("im")
```

We can use these inside our functions to help us build up comparison logic.


## Filter Arrays of Strings
```js
const isLindquist = name => name.includes("Lindquist")
const isWilkes = name => name.includes("Wilkes")

const lindquists = people.filter(isLindquist)
//lindquists is new Array with two strings: ["John Lindquist", "Mindy Lindquist"]
const wilkes = people.filter(isWilkes)
//wilkes is a new Array with one string: ["Kim Wilkes"]
```

## Customizing a Function
`isLindquist` and `isWilkes` are very specific functions, we'd rather be able
to create functions to support any last name. So let's make a function that
makes functions 😉

```js
const people = ["Kim Wilkes", "John Lindquist", "Mindy Lindquist"]
//See the two =>'s? This function outputs a function!
const isLastName = lastName => name => name.includes(lastName)

/*
  isLindquist is now the same function as before:
  const isLindquist = name => name.includes("Lindquist")
  only this time, we create it from the isLastName function.
*/
const isLindquist = isLastName("Lindquist")

const isWilkes = isLastName("Wilkes")

const lindquists = people.filter(isLindquist)
//lindquists is new Array with two strings: ["John Lindquist", "Mindy Lindquist"]
const wilkes = people.filter(isWilkes)
//wilkes is a new Array with one string: ["Kim Wilkes"]
```
