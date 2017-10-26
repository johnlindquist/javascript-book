## Put Your Logic Inside Functions

```js
const add = (x, y)=> x + y

const result = add(2, 3)
```

```diff
-const two = 2
-const three = 3
+const add = (x, y)=> x + y
 
-const result = two + three 
+const result = add(2, 3) 
```