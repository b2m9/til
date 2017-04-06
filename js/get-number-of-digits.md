# Get number of digits of positive integer

Similar to the problem [to get the n-th digit of a positive integer](get-nth-digit-of-number.md),
 one can easily determine the length of a positive integer without converting
  it to a string first by using `Math.log10`:
  
```javascript
// Truncate float via bitwise OR 0
Math.log10(1234567) + 1 | 0

// Or use Math.floor
Math.floor(Math.log10(1234567) + 1)
```

Since `Math.log10` is not supported by Internet Explorer, here is a polyfill 
by Mozilla. [1] 

```javascript
Math.log10 = Math.log10 || function(x) {
  return Math.log(x) * Math.LOG10E
}
```

References:

- [1] [MDN: Math.log10](https://developer.mozilla
.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log10)
