---
title: deepFreeze
tags: object,recursion,intermediate
---

# Deep freezes an object.

Use `Object.keys()` to get all the properties of the passed object, `Array.prototype.forEach()` to iterate over them.
Call `Object.freeze(obj)` recursively on all properties, checking if each one is frozen using `Object.isFrozen()` and applying `deepFreeze()` as necessary.
Finally, use `Object.freeze()` to freeze the given object.

```js
const deepFreeze = obj => {
  Object.keys(obj).forEach(prop => {
    if (obj[prop] === 'object' && !Object.isFrozen(obj[prop])) deepFreeze(v[prop])
  })
  return Object.freeze(obj)
}
```

```js
'use strict'

const o = deepFreeze([1, [2, 3]])

o[0] = 3 // not allowed
o[1][0] = 4 // not allowed as well
```
