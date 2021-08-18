Array.prototype.values()
========================

The `values()` method returns a new `Array Iterator` object that contains the values for each index in the array.

Syntax
------

    values()

### Return value

A new [`Array`](../array) iterator object.

Examples
--------

### Iteration using for...of loop

    var arr = ['a', 'b', 'c', 'd', 'e'];
    var iterator = arr.values();

    for (let letter of iterator) {
      console.log(letter);
    }  //"a" "b" "c" "d" "e"

**Array.prototype.values** is default implementation of **Array.prototype\[Symbol.iterator\]**.

    Array.prototype.values === Array.prototype[Symbol.iterator]      //true

### Iteration using .next()

    var arr = ['a', 'b', 'c', 'd', 'e'];
    var iterator = arr.values();
    iterator.next();               // Object { value: "a", done: false }
    iterator.next().value;         // "b"
    iterator.next()["value"];      // "c"
    iterator.next();               // Object { value: "d", done: false }
    iterator.next();               // Object { value: "e", done: false }
    iterator.next();               // Object { value: undefined, done: true }
    iteraror.next().value;         // undefined 

**Warning:** The array iterator object is one use or temporary object

example:

    var arr = ['a', 'b', 'c', 'd', 'e'];
     var iterator = arr.values();
     for (let letter of iterator) {
     console.log(letter);
    } //"a" "b" "c" "d" "e"
    for (let letter of iterator) {
    console.log(letter);
    } // undefined

**reason:** When `next().done=true` or `currentIndex>length` the `for..of` loop ends. See [Iteration protocols.](../../iteration_protocols)

**Value**: there are no values stored in the array Iterator object; instead it stores the address of the array used in its creation and so depends on the values stored in that array.

    var arr = ['a', 'b', 'c', 'd', 'e'];
    var iterator = arr.values();
    console.log(iterator);        // Array Iterator {  }
    iterator.next().value;        // "a"
    arr[1]='n';
    iterator.next().value;        //  "n"

**Note:** If the values in the array changed the array iterator object values change too.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.values">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'Array.prototype.values' in that specification.</span></a></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`values`

66

12

60

No

53

9

66

66

60

47

9

9.0

See also
--------

-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype.entries()`](entries)
-   [`Array.prototype.forEach()`](foreach)
-   [`Array.prototype.every()`](every)
-   [`Array.prototype.some()`](some)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/array.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values</a>
