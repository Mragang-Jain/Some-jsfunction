---
title: My Second Post!
---

> Map Function

The Map object holds key-value pairs and remembers the original insertion order of the keys. Any value (both objects and primitive values) may be used as either a key or a value.

> Description

The Map object holds key-value pairs and remembers the original insertion order of the keys. Any value (both objects and primitive values) may be used as either a key or a value.

- Key equality is based on the sameValueZero algorithm.
- NaN is considered the same as NaN (even though NaN !== NaN) and all other values are considered equal according to the semantics of the === operator.
- In the current ECMAScript specification, -0 and +0 are considered equal, although this was not so in earlier drafts. See "Value equality for -0 and 0" in the Browser compatibility table for details.

> let wrongMap = new Map()
>
> wrongMap['bla'] = 'blaa'
>
> wrongMap['bla2'] = 'blaaa2'
>
> console.log(wrongMap) // Map { bla: 'blaa', bla2: 'blaaa2' }

## Using the Map object

> let myMap = new Map()
>
> let keyString = 'a string'
> let keyObj = {}
> let keyFunc = function() {}
>
> // setting the values
> myMap.set(keyString, "value associated with 'a string'")
> myMap.set(keyObj, 'value associated with keyObj')
> myMap.set(keyFunc, 'value associated with keyFunc')
>
> myMap.size // 3
>
> // getting the values
> myMap.get(keyString) // "value associated with 'a string'"
> myMap.get(keyObj) // "value associated with keyObj"
> myMap.get(keyFunc) // "value associated with keyFunc"
>
> myMap.get('a string') // "value associated with 'a string'"
> // because keyString === 'a string'
> myMap.get({}) // undefined, because keyObj !== {}
> myMap.get(function() {}) // undefined, because keyFunc !== function () {}
