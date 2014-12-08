#filter() and map()

Like `forEach()`, `filter()` and `map()` allow any arbitrary function to be applied to an array.

`filter()` will return a subset of the input array, only including items that return true from the function.

`map()` will return a new array created by applying the function to each of the elements of the input array.

These functions can be combined to both filter and map some input array to return a new array. Try the exercise below.

---  
Filter and map the input to get a simple list of names of those entries that have an img attribute.

```js 
var results = [
    { id: 123, name: 'one' , img: "one.jpg" },
    { id: 124, name: 'two' },
    { id: 125, name: 'three', img: "three.jpg" },
    { id: 126, name: 'four' }
];
var hasImg = function(item) {
    return item.img; 
}
var name = function(item) { 
    return item.name; 
}

var out = results. ;
```  

```js 
var results = [
    { id: 123, name: 'one' , img: "one.jpg" },
    { id: 124, name: 'two' },
    { id: 125, name: 'three', img: "three.jpg" },
    { id: 126, name: 'four' }
];
var hasImg = function(item) {
    return item.img; 
}
var name = function(item) { 
    return item.name; 
}

var out = results.filter(hasImg).map(name);
```  
```js 
assert(out[1] == 'three');
```  
---
