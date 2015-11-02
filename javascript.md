
# Javascript

### Never use `eval`
### Never use `with`

### Random tips

* Use `Array.isArray(x)` over `x instanceOf Array` where possible
* Use `parse{Int, Float}(x)` instead of `+x`
* Use `x.toString()` instead of `String(x)`
* Check that constructor is called with new, else return new instance
```js
function X() {
  if(!(this instanceof X)) return new X();
}
```
* `if(~arr.indexOf(x)) {` is a neater way to check if Array has item than `if(arr.indexOf(x) >= 0) {`
* Return early for uncommon branches
```js
function hello(callback) {
  doSomething(function(err) {
    if(err) {
      return callback(err);
    }
    finish()
  });
}
```
instead of:
```js
function hello(callback) {
  doSomething(function(err) {
    if(!err) {
      finish();
    } else {
      return callback();
    }
  })
}
```

### Performance tips

* Don't worry about extracting `len` into another variable before you iterate over something, JS engine will do it for you.
 * `for(var i = 0, len = arr.length; i < len; i++) {`
 * https://jsperf.com/caching-array-length/7
