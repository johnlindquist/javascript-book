## Conditionals

### If this, then that, otherwise the other
```js
const age = 72
const isSenior = age => age > 65 

const ticketPrice = isSenior(age)
  ? "$5.00"
  : "$8.50"
```

### If this or that
```js
const buyerChild = 7
const buyerSenior = 67

const isSenior = age => age > 65 
const isChild = age => age < 8

const isDiscount = age => isSenior(age) || isChild(age)

const ticketPrice = isDiscount(age)
  ? "$5.00"
  : "$8.50"
```