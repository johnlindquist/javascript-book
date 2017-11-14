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

> ** [info] Looking Ahead: Functions Can Make Functions **
>
`isLindquist` and `isWilkes` are very specific functions, we'd rather be able
to create functions to support any last name. So let's make a function that
makes functions 😉

>```js
const people = ["Kim Wilkes", "John Lindquist", "Mindy Lindquist"]
//See the two =>'s? The function with the lastName input outputs a function
with a name input!
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
>```
> We'll explore useful utilities that help with this style later

## Change Arrays of Strings with `.map`

First, let's create a function that can say "Hi" to anyone:

```js
const sayHi = name => `Hi, ${name}`
const hiKim = sayHi("Kim")// "Hi, Kim"
const hiJohn = sayHi("John") // "Hi, John"
const hiMindy = sayHi("Mindy")// "Hi, Mindy"
```

Now we can use our `sayHi` function on our Array of people with `.map`:

```js
const people = ["Kim", "John", "Mindy"]
const hiPeople = people.map(sayHi)
//hiPeople is now ["Hi, Kim", "Hi, John", "Hi, Mindy"]
```

## Get a Part of a String with `charAt` or `slice`
We can pull out individual letters from a String with `charAt`:
```js
const getFirstLetter = word => word.charAt(0)
const j = getFirstLetter("joy") //"j"
const K = getFirstLetter("Kim") //"K"
const M = getFirstLetter("Mindy") //"M"
```

`0` is the beginning of the String, `1` is the second, `2` is third, and so on.
We call this, "zero-based index", where you begin counting at `0`. If it helps,
think of `0` as a marker to the left of the first letter and `1` as a marker
to the right so that if you want the first letter, you're asking for the letter
between `0` and `1`.

We can further demonstrate this with `.slice`. `.slice` takes a start index
and and end index and gives you every character in-between:
```js
//The letter between 0 and 1 is the first letter
const getFirstLetter = word => word.slice(0, 1)

//The letters between 0 and 2 are the first and second letter
const getFirstAndSecondLetter = word => word.slice(0, 2)

//The letters between 1 and 3 are the second and third letters
const getSecondAndThirdLetter = word => word.slice(1, 3)

const K = getFirstLetter("Kim") //"K"
const Ki = getFirstAndSecondLetter("Kim") //"Ki"
const im = getSecondAndThirdLetter("Kim") //"im"
```

We can use our new functions with Array and `.map` just like before:
```js
const people = ["Kim", "John", "Mindy"]
const secondAndThirdLetters = people.map(getSecondAndThirdLetter)
//secondAndThirdLetters is ["im", "oh", "in"]
```

## Get the End of a String with `.length`
`.length` is a property on a String that tells you the index to the right
of the last character:
```js
"Kim".length //3
"John".length //4
"Mindy".length //5
```

<br>
So getting an entire String would start at `0` (to the left of the first character) and end at `.length` (to the right of the last character).

> ** [danger] Remember, `.length` is _after_ the last character **
>```js
//Bad Example
const badGetLastLetter = word => word.charAt(word.length)
const badExample = badGetLastLetter("Kim") //""
//The index of .length comes after the word, so it can't find a letter
//Good Example. Notice the -1
const goodGetLastLetter = word => word.charAt(word.length - 1)
const goodExample = goodGetLastLetter("Kim") //"m"
//Move the index one to the left with `-1`, then we're looking in the right spot
>```

Using `.slice`, we can easily grab the final letters off of a String. `-1` is a
valid index to slice (meaning the index before `.length`), so we could simply
start at -1. The second argument of `.slice` defaults to the `.length` of the
String, so we can actually leave it out:
```js
"Kim".slice(-1, "Kim".length) //"m"
//is the same as
"Kim".slice(-1) //"m"
```

So our functions would look like this:
```js
const getLastLetter = word => word.slice(-1)
const getLastTwoLetters = word => word.slice(-2)
const getLastThreeLetters = word => word.slice(-3)

const y = getLastLetter("Mindy") //"y"
const dy = getLastTwoLetters("Mindy") //"dy"
const ndy = getLastThreeLetters("Mindy") //"ndy"
``` 

## `.slice` works on Arrays too!
You can use what you learned with `.slice` and apply that exact same thinking
to Arrays:
```js
const people = ["Kim", "John", "Mindy", "Ben", "Lisa"]

const getFirst = array => array.slice(0, 1)
const getLast = array => array.slice(-1)
//You can also use -1 as an end index to slice to before the last item
const getMiddle = array => array.slice(1, -1)

const first = getFirst(people) //["Kim"]
const last = getLast(people) //["Lisa"]
const middle = getMiddle(people) //["John", "Mindy", "Ben"]
```

> ** [info] Looking Ahead: Function Composition **
> Functions that have Arrays as input and output can work together:
>```js
//getMiddle is called with people, then getFirst is called with that result
const getFirstOfMiddle = array => getFirst(getMiddle(array))
const firstOfMiddle = getFirstOfMiddle(people) // ["John"]
>```
> There are useful utilities to help compose functions that we'll explore later


## Put Arrays Back Together with `...`
`...` refers to "spreading", so you can take all the items in an Array
and spread them into another Array:
```js
const first = ["Kim"]
const middle = ["John", "Mindy", "Ben"]
const last = ["Lisa"]

const all = [...first, ...middle, ...last] 
//all is now ["Kim", "John", "Mindy", "Ben", "Lisa"]
```

## Get an Item from an Array by Index
Often, instead of an Array, you just want a single Item from the Array:

```js
const array = ["a", "b", "c", "d", "e", "f"]

//Notice the index surrounded by [], a colon :, then the name
const {[0]:first} = array // first is now "a"
const {[2]:third} = array // third is now "c"
const {[array.length - 1]:last} = array // last is now "f"
```

You can even combine these into a single statement:
```js
const array = ["a", "b", "c", "d", "e", "f"]

const {[0]:first, [2]:third, [array.length - 1]:last} = array
//Again, first is "a", third is "c", and last is "f"
```

You will often see a statement like the one above spread across multiple
lines for readability:

```js
//The EXACT SAME as above
const array = ["a", "b", "c", "d", "e", "f"]

const {
  [0]:first, 
  [2]:third, 
  [array.length - 1]:last
} = array

```

## Get a Random Item from an Array
For many games and apps, you'll want to select something from an
Array at random. A typical `getRandomIndex` leverages the functions
built on `Math`:

```js
const getRandomIndex = array => Math.floor(Math.random() * array.length)
```

Let's break this down piece by piece:
```js
Math.random() //Generates a random number between 0 - 1 e.g. 
/*
Examples:
0.2195010408727054
0.6597169504828302
0.34967492089264995
*/
Math.random() * array.length
/*
  Generates a random number between 0 and the length of the Array
*/
Math.floor(0.4) //rounds down to 0
Math.floor(8.9) //rounds down to 8
Math.floor(100.987523) //rounds down to 100

Math.floor(Math.random() * array.length)
/*
  Rounds the random number down to a proper index
*/
```

Putting it all together:
```js
const array = ["a", "b", "c", "d", "e", "f"]
const getRandomIndex = array => Math.floor(Math.random() * array.length)

const randomIndex = getRandomIndex(array)

const {[randomIndex]:randomItem} = array
```