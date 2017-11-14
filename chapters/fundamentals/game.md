## Higher or Lower Game
```js
import { render } from "react-dom"

const element = document.getElementById("app")

const increment = value => value + 1
const makeRandomNumber = limit =>
  Math.floor(Math.random() * limit)

const game = {
  answer: makeRandomNumber(100),
  guess: -1,
  saveGuess(guess) {
    this.guess = guess
  },
  attempts: 0,
  attempt() {
    this.attempts = increment(this.attempts)
  }
}

const setGuess = event => game.saveGuess(event.target.value)

const makeGuess = event => {
  game.attempt()
  render(<App {...game} />, element)
}

const checkGuess = ({ guess, answer }) =>
  guess > answer
    ? "Too high"
    : guess < answer ? "Too low" : "Correct"

const App = props => (
  <div>
    <input onChange={setGuess} />
    <button onClick={makeGuess}>Guess</button>
    <div>Attempts: {props.attempts}</div>
    <div>{checkGuess(props)}</div>
  </div>
)

render(<App {...game} />, element)
```