## Conditionals

Much of programming is built on whether a condition is met: Is the item in
stock? Is there a sale? Do you have a coupon?

JavaScript provides an easy way to check the `true/false` condition then
give you back something if true or false:

### If this, then A, otherwise B
```js
const isSenior = age => age > 65 

const ticketPrice = isSenior(75)
  ? "$5.00"
  : "$8.50"

//The ticketPrice is "$5:00"
```

### If this ***OR*** that
```js
const isSenior = age => age > 65 
const isChild = age => age < 8

const isDiscount = age => isSenior(age) || isChild(age)

const ticketPrice = isDiscount(age)
  ? "$5.00"
  : "$8.50"
```

### If this ***AND*** that
```js
const kitchen = ["sugar", "flour"]
const inStock = item => kitchen.includes(item)

const canMakeCookies = inStock("sugar") && inStock("flour")
```