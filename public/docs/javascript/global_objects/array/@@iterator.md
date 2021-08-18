Array.prototype\[@@iterator\]()
===============================

The `@@iterator` method is part of [The iterable protocol](../../iteration_protocols#the_iterable_protocol), that defines how to synchronously iterate over a sequence of values.

The initial value of the `@@iterator` property is the same function object as the initial value of the [`values()`](values) property.

Syntax
------

    [Symbol.iterator]()

### Return value

The initial value given by the [`values()`](values) **iterator**. By default, using `arr[Symbol.iterator]` will return the [`values()`](values) function.

Examples
--------

### Iteration using for...of loop

#### HTML

    <ul id="letterResult">
    </ul>

#### JavaScript

    const arr = ['a', 'b', 'c'];
    const eArr = arr[Symbol.iterator]();
    const letterResult = document.getElementById('letterResult');
    // your browser must support for..of loop
    // and let-scoped variables in for loops
    // const and var could also be used
    for (let letter of eArr) {
      const li = document.createElement('LI');
      li.textContent = letter;
      letterResult.appendChild(li);
    }

#### Result

### Alternative iteration

    var arr = ['a', 'b', 'c', 'd', 'e'];
    var eArr = arr[Symbol.iterator]();
    console.log(eArr.next().value); // a
    console.log(eArr.next().value); // b
    console.log(eArr.next().value); // c
    console.log(eArr.next().value); // d
    console.log(eArr.next().value); // e

### Use Case for brace notation

The use case for this syntax over using the dot notation (`Array.prototype.values()`) is in a case where you don't know what object is going to be ahead of time. If you have a function that takes an iterator and then iterate over the value, but don't know if that Object is going to have a \[Iterable\].prototype.values method. This could be a built-in object like [String](../string/@@iterator) object or a custom object.

    function logIterable(it) {
     if (!(Symbol.iterator in Object.getPrototypeOf(it)
     /* or "Symbol.iterator in Object.__proto__"
        or "it[Symbol.iterator]" */)) {
       console.log(it, ' is not an iterable object...');
       return;
     }

     var iterator = it[Symbol.iterator]();
      // your browser must support for..of loop
      // and let-scoped variables in for loops
      // const and var could also be used
      for (let letter of iterator) {
          console.log(letter);
      }
    }

    // Array
    logIterable(['a', 'b', 'c']);
    // a
    // b
    // c

    // string
    logIterable('abc');
    // a
    // b
    // c

    logIterable(123);
    // 123 " is not an iterable object..."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype-@@iterator">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype-@@iterator</span></a></td></tr></tbody></table>

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

`@@iterator`

38

12

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

No

25

10

38

38

36

27-36

A placeholder property named `@@iterator` is used.

17-27

A placeholder property named `iterator` is used.

25

10

3.0

See also
--------

-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype.entries()`](entries)
-   [`Array.prototype.forEach()`](foreach)
-   [`Array.prototype.every()`](every)
-   [`Array.prototype.some()`](some)
-   [`Array.prototype.values()`](values)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@iterator</a>
