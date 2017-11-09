## More Functions

The logic of a function often needs more than
one line to fully express:

```js
const makeUsername = (name, date) => {
  const lowercaseName = name.toLowerCase()
  const year = date.getFullYear()
  
  return `${lowercaseName}${year}`
}
```