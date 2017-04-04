# Number's toString() method to convert numbers

`Number` does not simply inherit `toString` from `Object`. Instead it overrides
the method and takes a parameter `radix`. The parameter can be any value
between 2 and 32, if not set it will default to 10. Negative numbers are
preserved. [1]

```javascript
(255).toString(16) // Returns 'ff'
(10).toString(2) // Returns '1010'
(-512).toString(16) // Returns '-200'
```

References:

- [1] [MDN: Number.prototype.toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString)
