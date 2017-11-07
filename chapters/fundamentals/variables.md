# Variables

Programming is all about taking some input, doing something with it,
then outputting it somehow. An online form would take your information,
validate it, then submit it to create an account. A video game would
take a button press, map it to a jump action, then trigger the character to jump
on the screen.

```js
const two = 2
const four = 2 + 2
const six = two + four
```

What are these 3 lines? Why is the `=` to the left of the addition? And what's with those weird words at the start?

### `const` is a _keyword_ that starts _statements_.
You will always find `const` at the beginning of the line of code
because `const` tells you that what is coming next is a name (like `four`), an assignment (`=`), then an expression (`2 + 2`).

### The variable name
You can name variables almost anything, but the most common is to use a
camel-cased group of words to describe the expression: `order`, `carDestination`, `pizzasConsumed`, `removedPosts`, `likedVideos`. You'll find the full set of 
variable naming rules in the appendix.

### `=` represents an _assignment_.

Each expression after the `=` is evaluated then _assigned_ to the name on the left.

For example, `2` is evaluated then assigned the name `two`. So from now on, if
you use `two` in your code base, it will represent the number `2`.

In the second line, `2 + 2` is evaluated then assigned to the word `four`. So
JavaScript will only have to evaluate `2 + 2` once and from then on out, you can
just use `four` to represent the result of `2 + 2` (which is 4).

On the third line, we're taking our `two` variable and `four` variable, adding 
them together, then assigning them to the name `six`. 

## The expression

An expression can be as simple as the number `1`. JavaScript will evaluate `1`
and give you the value of `1`. Simple, right? An expression can also evaluate
math, dates, and all varieties of functions which we'll explore later.

## Statements in a nutshell
```js
//start statement, name, assignment, expression
const myVariable = 1 + 1
```

> ** [success] Good Examples **
> ```
const firstName = "Kim"
const age = 22
const pet = false
>```

<br>

> ** [danger] Bad Examples **
> ```
firstName const = "Kim"
firstName = const "Kim"
firstName = "Kim" const
>```


## Strings
```js
const firstName = "Kim"
const lastName = "Wilkes"
const planet = "Earth"
```

Unlike numbers, letters and words need quotation marks `""` around them. The 
`""`'s let JavaScript know that you want them to be a "string of characters".

> ** [danger] What if I forget `""`'s? **
>```js
const firstName = Kim
/*
  JavaScript will look for a variable named Kim,
  when it can't find Kim, you'll get this error:
  Uncaught ReferenceError: Kim is not defined
*/
>```


## Combining Strings and Multi-line Strings
```js
const sentence = `${firstName} ${lastName} lives on planet ${location}`
const haiku = `
From time to time
The clouds give rest
To the moon-beholders.
`
```

The backtick `` ` `` starts and ends long strings. It even gives you the extra
feature of evaluating variables inside of your strings. Look at the sentence
above and you'll see `${}` surround names of variables. Those names will be
evaluated and placed into the string.


## True and False
```js
const isKimCool = true
```

`true` and `false` are called "booleans" in programming. They're most often
used as the result of a comparison which we'll talk more about in our
chapter on functions.



<br>

> ** [info] Ending a line with semi-colons `;` **
>
> Semi-colons `;` are optional in the vast
> majority of situations, but you'll see many,
> many people who prefer to use them to end lines.

