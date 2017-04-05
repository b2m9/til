# Get n-th digit from number

Recently, I had the problem to get the n-th of a number in JavaScript. I 
wanted to find a better solution than the obvious way to convert it to a 
string, like: `('' + number)[index]`.

Here is a pretty elegant way to divide the number by the length of the number
 until the n-th digit to get the relevant digits:

```javascript
// Get 4-th digit from 123456789
let digit = getDigit(123456789, 3)  // returns 3

function getDigit (n, i) {
  // n... positive integer
  // i... index of digit
  const length = Math.pow(10, Math.floor(Math.log10(n)) - (i - 1))
  const base = Math.floor(n / length)
  
  // Calculate difference between result of division and "flattened" number
  return base - (Math.floor(base / 10) * 10)
}
```

Kudos to Danys Séguret on Stack Overflow. [1]

The respective JSPerf shows that it is much faster than converting it to a 
string. [2]

References:

- [1] [Stack Overflow](http://stackoverflow.com/questions/13955738/javascript-get-the-second-digit-from-a-number)
- [2] [JSPerf test](http://jsperf.com/get-second-digit)
