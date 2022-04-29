# JS cheat sheet

## Array manipulation methods

Those examples was made from **node CLI**

```js
> var doo = ['a', 'b', 'c']
undefined
```

> Creating a simple array

---

### Reverse

```js
> doo.reverse()
[ 'c', 'b', 'a' ]
```

> Reverse method will just reverse our array

---

### ForEach

```js
> doo.forEach(s => console.log(s))
a
b
c
undefined
```

> Creating a loop using the method forEach, but we also are able to do that using `map()`

### Using Map

```js
> doo.map(a => a)
[ 'a', 'b', 'c' ]
```

We are also able to do more things using map()

```js
> doo.map(a => a + ' xss')
[ 'a xss', 'b xss', 'c xss' ]
```

> We are able to concatenate string

Below we can see examples using map:

```js
> var numr = [1, 2, 3, 4, 5]
undefined

> numr
[ 1, 2, 3, 4, 5 ]

> numr.map(a => a)
[ 1, 2, 3, 4, 5 ]

> numr.map(a => a+1)
[ 2, 3, 4, 5, 6 ]

> numr.map(a => a*2)
[ 2, 4, 6, 8, 10 ]

> numr.map(a => a+' pos')
[ '1 pos', '2 pos', '3 pos', '4 pos', '5 pos' ]

```

Anothe example using objects:

```js
> var obj = [{name: 'jos', age: 12}, {name: 'nika', age: 23}]
undefined

> obj
[ { name: 'jos', age: 12 }, { name: 'nika', age: 23 } ]

> obj.map(a => a)
[ { name: 'jos', age: 12 }, { name: 'nika', age: 23 } ]

> obj.map(a => a.name)
[ 'jos', 'nika' ]

> obj.map(a => a.age)
[ 12, 23 ]

> obj.map(a => a.name +' '+ a.age)
[ 'jos 12', 'nika 23' ]

```

## String manipulation

Here we create a simple array with string

```js
> var tt = ['sd', 'dasda', 'SADAD']
undefined
> tt
[ 'sd', 'dasda', 'SADAD' ]

```

### Upper Case

Here we will upper case the index 0

```js
> tt[0].toUpperCase()
'SD'
```

And also we can lower case the index 2

### Lower Case

```js
> tt[2].toLowerCase()
'sadad'
```

---

Anothe example, manipulating a string

```js
> var st = 'AAAA SSSSS'
undefined
```

And then, we will replace that string `AAAA`

### Replace

```js
> st.replace('AAAA', 'AXAX')
'AXAX SSSSS'
```

> As we can see, the method replace works like that `replace(current_string, new_string)`

---

Now we will se how to slice a string:

### Slice

```js
> var st2 = st.replace('AAAA', 'AXAX')
undefined
> st2.slice(3)
'X SSSSS'
```

> Here, the st2 is a variable where exists that string `AXAX SSSSS`, so the slice will delete 3 characteres from the beginning, for example `[AXA]X SSSSS`
>> If we put -3 we will delete 3 characteres from the final

---

Using the split

### Split

```js
> var aa = 'AAA SS DD'
undefined
> aa
'AAA SS DD'

```

Now we will split that string, to do that, we will put in the parameter of method, which kind of string we will use to separate a group of string. I will use the space to create a array of strings

```js
> aa.split(" ")
[ 'AAA', 'SS', 'DD' ]
```

Let's suppose that we have a comma, and we will use that comma to be a reference to divide our group of string

```js
> var bb = 'sasa, aa, dd, gg'
undefined
> bb
'sasa, aa, dd, gg'
> bb.split(",")
[ 'sasa', ' aa', ' dd', ' gg' ]

```
