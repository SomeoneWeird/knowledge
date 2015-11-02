
# Javascript

### Random tips

* Use `Array.isArray(x)` over `x instanceOf Array` where possible
* Use `parse{Int, Float}(x)` instead of `+x`
* Check that constructor is called with new, else return new instance
```js
function X() {
  if(!(this instanceof X)) return new X();
}
```

### Performance tips

* Don't worry about extracting `len` into another variable before you iterate over something, JS engine will do it for you.
 * `for(var i = 0, len = arr.length; i < len; i++) {`
 * https://jsperf.com/caching-array-length/7
