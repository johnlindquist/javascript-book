## Open a Terminal and Run Node.js

1. Open a Terminal on your computer
2. Type `node`

<br>
You should see a `>` pop up beneath your `node` command. You can now enter JavaScript and Node.js will evaluate it for you. This is called the Node.js REPL (Read Evaluate Print Loop). This mean Node.js will read each expression, evaluate it, then print out what it evaluates so you can see the result.

> [info] Exiting the Node.js REPL
>
> At any time, type `.exit` then hit `Enter` to exit out of the Node.js REPL and go back to normal Terminal bash commands.

## Your First Line of JavaScript
In your Terminal, in the Node.js REPL, type the following

```js
2 + 3
```

> [danger] Probably need screenshots to help build confidence

The terminal should respond with

```js
5
```

> [success] Congratulations! You know JavaScript! :wink:

## Write Code in Editors, Not REPLs

You can spend all day writing things into the Node.js REPL:

```js
"batman!".toUpperCase()
```

or

```js
new Date().toString()
```

or even

```js
["I", "love", "cheese"].map(word => word.toUpperCase() + "!").join(" ")
```

but _real_ development is done in a Code Editor like VS Code. None of this code is saved It's important to understand that Node.js will be running behind the scenes in many of the tools that you'll be using everyday, but we're going to go through a few more setup steps to make our lives a billion times easier. Trust me, it's worth it.



