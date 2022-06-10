# JS functional

## Currying

First example

```js

> const add = a => b => a+b
undefined

> const sub = a => b => a-b
undefined

> const mult = a => b => a*b
undefined

> const div = a => b => a/b
undefined

```

> Here we are using arrow function. We are creating 4 arithmetic functions

```js

> add(1)(1)
2

> sub(5)(2)
3

> mult(2)(10)
20

```

```js

> const arith = funcHere => a => b => funcHere(a)(b)
undefined

```

>Now we are creating a new Function `arith` where this function will receive another function B, and we will be able to use the function A (arith) by function B

```js

> arith(mult)(2)(5)
10

```

> The `mult` function will use de `a` and `b` from function `arith`
