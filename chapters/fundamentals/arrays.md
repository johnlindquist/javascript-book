# Arrays

More often than not, you'll be working with a collection of data: Users
of an app, posts on a blog, timestamps on a video, or any group of related
types that all belong together. This is where arrays come in:

```js
const myNumbers = [1, 2, 3]
const myPeople = ["Kim Wilkes", "John Lindquist", "Mindy Lindquist"]
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


