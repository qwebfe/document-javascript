---
title: compactWhitespace
tags: string,regexp,beginner
---

# Returns a string with whitespaces compacted.

Use `String.prototype.replace()` with a regular expression to replace all occurrences of 2 or more whitespace characters with a single space.

```js
const compactWhitespace = str => str.replace(/\s{2,}/g, ' ')
```

```js
compactWhitespace('Lorem    Ipsum') // 'Lorem Ipsum'
compactWhitespace('Lorem \n Ipsum') // 'Lorem Ipsum'
```
