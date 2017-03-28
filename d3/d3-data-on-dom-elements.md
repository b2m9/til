# Where d3 stores data in DOM elements 

While debugging d3.js visualisations, it can be helpful to actually see if
DOM elements have the correct data points. 

d3 stores the corresponding data point of every DOM element in the `__data__` 
property of the element itself.

This is also the case, if the DOM element isn't reflecting any _new data_.
Example:

```html
<ul>
    <li>A</li>
    <li>B</li>
    <li>C</li>
</ul>
```

```javascript
d3.selectAll('li').data([1, 2, 3, 4])
  .enter().append('li')
    .text(function (d) { return d })
```

The code would only append a list item with the content `4`, because it only 
executes the `enter()` selection.

However, in debugging this issue one can find out that d3 correctly bound the 
new data to the previous DOM elements by examining their `__data__` property:

```javascript
d3.selectAll('li')._groups[0].forEach(function (el) {
  console.log(el.__data__)
  // Logs 1, 2, 3, 4
})
```
