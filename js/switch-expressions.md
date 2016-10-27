# Switch and evaluating expressions

The `switch` statement is common across many languages. However, I was not
aware of how to use `switch` for expressions instead of values. 

A simple function that takes `age` as a parameter:

```javascript
function foo (age) {
  if (age > 30) {
    // ...
  } else if (age > 20) {
    // ...
  } else if (age > 10) {
    // ...
  } else {
    // ...
  }
}
```

This logic won't work with `switch`, at least not as straight forward as I
assumed. Because `switch` is __strictly comparing__ the result of the input
expression to the value of each `case`. [1]

Therefore, the following code doesn't work as expected. It would always return 
the `default` case:

```javascript
switch (age) {
  case (age > 30):
    // ...
    break
  case (age > 20):
    // ...
    break
  case (age > 10):
    // ...
    break
  default:
    // ...
}
```

To match the strict comparison, `switch` can be simply provided with `true`.

```javascript
function foo (age) {
  switch (true) {
    case (age > 30):
      // ...
      break
    case (age > 20):
      // ...
      break
    case (age > 10):
      // ...
      break
    default:
      // ...
   }
}
```

Once again, credits go to Stack Overflow. [2]

References:
- [1] [MDN: Switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
- [2] [Stack Overflow](http://stackoverflow.com/questions/3463833/expression-inside-switch-case-statement)