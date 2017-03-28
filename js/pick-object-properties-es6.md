# Pick object properties with ES6

Fans of [lodash's pick functionality](https://lodash.com/docs/4.16.6#pick) can
use ES6's destructing and shorthand literals instead:

```javascript
const response = {
  data: [1, 2, 3, 4],
  key: 'key',
  meta: {},
  ref: 'ref'
}

// lodash
_.pick(response, ['data', 'key'])
// returns { data: [1, 2, 3, 4], key: 'key' }

// ES6
const {data, key} = response
// creates variables `data` and `key` with respective values
```

Kudos to Nicolás Bevacqua's great blog post [1].

References:

- [1] [Pony Foo: ES6 Object Literal Features in Depth](https://ponyfoo.com/articles/es6-object-literal-features-in-depth) 
