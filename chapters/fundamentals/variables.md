Programming is all about taking some input, doing something with it,
then outputting it somehow. An online form would take your information,
validate it, then submit it to create an account. A video game would
take a button press, map it to a jump action, then trigger the character to jump
on the screen.

## Variables

```js
const four = 2 + 2
```
```js
let four = 2 + 2
```
```js
var four = 2 + 2
```

#### What are these 3 lines?

Each seem to accomplish the task of adding `2` and `2`, but 
why is the `=` to the left of the addition? And what's with those weird words at the start.

`=` represents an _assignment_.

So each `2 + 2` evaluated then _assigned_ to the name on the left.

`four` is a _variable_.

Each `four` will now be a reference to the number "4" because `2 + 2` has been evaluated.

`const`, `let`, and `var` are _keywords_ that start _statements_.
You will always find them at the beginning of the line of code
because they tell you that what is coming next is a name (like `four`), an assignment (`=`), then an expression (`2 + 2`).


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

#### const, let, and var

In short:

* Use `const` almost always
* Use `let` when needed
* Avoid `var`, but you'll see it _everywhere_

`const` prevents you from "re-assigning" the variable to something else. 
Re-assigning can cause unexpected bugs in your code.

> ** [danger] `const` prevents the following **
> ```
const name = "John"
name = "Kim"
//Uncaught TypeError: Assignment to constant variable.
>```

`let` allows you to "re-assign". We'll talk more about why you might want to
later in the book.

`var` has been around since JavaScript was first released as a language while
`const` and `let` are relatively new. When you Google for an answer to your
JavaScript questions, odds are the answer will include a `var`. This doesn't
mean the answer is wrong, simply that the answer is older than `const` and `let`
. `var` is a lot like `let` in that it allows you to re-assign, but also has
looser scoping. We'll discuss more about _scope_ later.



<br>

> ** [info] Ending a line with semi-colons `;` **
>
> Semi-colons `;` are optional in the vast
> majority of situations, but you'll see many,
> many people who prefer to use them to end lines.

