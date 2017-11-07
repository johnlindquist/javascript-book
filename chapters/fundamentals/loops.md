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

