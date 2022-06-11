# JS cheat sheet

## Array manipulation methods

Those examples was made from **node REPL**

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

### Slice

```javascript
> const arr = [1, 2, 3, 4, 5, 6, 7 ,8, 9, 10, 11]
undefined

> arr.slice(1,5)
[ 2, 3, 4, 5 ]

> arr.slice(3)
[
  4, 5,  6,  7,
  8, 9, 10, 11
]

```

>Slice we are able to specify the beginning and the final where we want to cut from an array

```javascript
> const arr = [1, 2, 3, 4, 5, 6, 7 ,8, 9, 10, 11]

> arr.slice(3, 8)
[ 4, 5, 6, 7, 8 ]

```

> This example, as we can see, we specify that we going to cut all number under 4, and cut all number above 8
>> It is important to notice, the number is the index for each value

```javascript
> const abc = ['a','b','c','d','e','f','g']
undefined
> abc.slice(3,5)
[ 'd', 'e' ]

```

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

---

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

---

### Using Filter

This method we use to filter a array, and in there we can add a condictional to filter it

```javascript
> const array = [1, 23, 44, 5, 6, 76, 767]
undefined
> array.filter(v => v > 10)
[ 23, 44, 76, 767 ]
> array.filter(v => v > 40)
[ 44, 76, 767 ]

```

---

### Using Reduce

```javascript
> const array2 = [1, 2, 3]
undefined
> array2.reduce((ac, val) => ac + val)
6
```
> In this example, we are adding all number inside of array, that means, we are doing this `1+2+3`, and then, to do that kind of operation, we can use reduce, where we are able to create operations and accumulate each result.
>> reduce we can use 4 values in the parameter, `accumulate`, `values_array`, `index_value`, `current_array`. In this example, `ac` is the accumulate and `val` is value

---

### Concat

This method will allow us to join arrays

```js
> a = [1,2,3]
[ 1, 2, 3 ]
> b = [11,22,33]
[ 11, 22, 33 ]
> j = a.concat(b)
[ 1, 2, 3, 11, 22, 33 ]
> j
[ 1, 2, 3, 11, 22, 33 ]
```

---

### Fill

Example to how fill an array with a specific valor

```js
> var aa = ['aa', 'bb', 'cc']
undefined
> aa.fill('xoxo')
[ 'xoxo', 'xoxo', 'xoxo' ]
> aa
[ 'xoxo', 'xoxo', 'xoxo' ]
```

---

### Join

Join allow us transform a array into a string, joing all the index

```js
> var ww = ['aaaa', 'bbbbb', 'uuuuuu']
undefined
> ww.join(" ")
'aaaa bbbbb uuuuuu'
> ww.join("-")
'aaaa-bbbbb-uuuuuu'
> ww.join(" -*- ")
'aaaa -*- bbbbb -*- uuuuuu'
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

---

### Repeat

Now, how to use the repeat method:

```js
> var hi = 'hi!'
undefined
> hi.repeat(3)
'hi!hi!hi!'
```

---

### Search

Search will show us the index of a string, if such string does not exist, the output will be -1

```js
> var st = 'A bb ccc'
undefined
> st.search("bb")
2
> st.search("A")
0
> st.search("ccc")
5
```

> As we can see, the `bb` string starts in the index 2, the `A` starts in the index 0

```js
> st.search("sssss")
-1
```

> If the string does not exist, the output is -1

---

### Trim

Trim is interesting, because it will delete from our string, useless spaces

```js
> var aa = '    sdad sad     dasd       '
undefined
> aa
'    sdad sad     dasd       '
> aa.trim()
'sdad sad     dasd'
```

> We can notice that trim delete space from the beginning and end of the string

---

## Functions

Here a example using annonymous function and arrow function

```js
> var x = () => 'hi'
undefined
> x
[Function: x]
> x()
'hi'
> var xx = function(){ return 'hello' }
undefined
> xx()
'hello'
> var ss = xx
undefined
> ss()
'hello'
```

---

## Spread operator

```javascript
> const ax = (...a) => `${a} --`
undefined

> ax(112,23,34,45,65)
'112,23,34,45,65 --'

> const bx = (a) => `${a} -- `
undefined

> bx(121,231,231,3123,32,342)
'121 -- '
```

> Spread operator `...` allows us to add multiples args into the parameter

```javascript
> const string = 'mariana'
undefined
> string
'mariana'
> const artring = [...string]
undefined
> artring
[
  'm', 'a', 'r',
  'i', 'a', 'n',
  'a'
]
```

> And also it allows us to transform a string into a array easily

```javascript
> const ar = [1,2,3]
undefined
> const ar2 = [ar]
undefined
> ar2
[ [ 1, 2, 3 ] ]
> const ar3 = [...ar]
undefined
> ar3
[ 1, 2, 3 ]
```

> Or avoid to add a array A into another array B, but transform the array A as a B