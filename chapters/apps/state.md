## State

Apps have "state". You click a button, something changes.  You type in a field, something else changes. All these changes need to be tracked somewhere. That's 
where "state" comes in.

Tracking state is broken into two pieces:
1. Create a new state from the old state
2. Save the new state

"Save" is sometimes called "setState", "commit", or any other variation of 
"take this new state and put it where the old one was".

Below is a simplified version of "Hangman".

Notice how the `game` Object has a `state` and a way to `save` the state, so
the cycle becomes:
1. Call `addGuess` with the guess and the old state
2. `addGuess` gives us back a new state
3. We save the new state with `game.save`

### Hangman
```js
const game = {
  state: {
    phrase: "Chance Favors the Prepared Mind",
    guesses: []
  },

  save(state) {
    this.state = state
  }
}

const addGuess = (letter, state) => ({
  ...state,
  guesses: [...state.guesses, letter]
})

game.save(addGuess("a", game.state))
game.save(addGuess("c", game.state))
game.save(addGuess("f", game.state))
game.save(addGuess("v", game.state))
game.save(addGuess("o", game.state))
game.save(addGuess("s", game.state))
game.save(addGuess("p", game.state))
game.save(addGuess("m", game.state))

const goodGuess = (guesses, letter) =>
  guesses.includes(letter.toLowerCase())

const isSpace = letter => letter == " "

const compare = (phrase, guesses) => {
  const arrayOfLetters = phrase.split("")
  const compared = arrayOfLetters.map(
    letter =>
      goodGuess(guesses, letter) || isSpace(letter)
        ? letter
        : "?"
  )

  const stringOfCompared = compared.join("")

  return stringOfCompared
}

const current = compare(
  game.state.phrase,
  game.state.guesses
)

//C?a?c? Favo?s ??? P??pa??? M???
```