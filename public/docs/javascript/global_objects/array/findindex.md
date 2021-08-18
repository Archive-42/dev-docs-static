Array.prototype.findIndex()
===========================

The `findIndex()` method returns the **index** of the first element in the array **that satisfies the provided testing function**. Otherwise, it returns `-1`, indicating that no element passed the test.

See also the [`find()`](find) method, which returns the **value** of an array element, instead of its index.

Syntax
------

    // Arrow function
    findIndex((element) => { ... } )
    findIndex((element, index) => { ... } )
    findIndex((element, index, array) => { ... } )

    // Callback function
    findIndex(callbackFn)
    findIndex(callbackFn, thisArg)

    // Inline callback function
    findIndex(function callbackFn(element) { ... })
    findIndex(function callbackFn(element, index) { ... })
    findIndex(function callbackFn(element, index, array){ ... })
    findIndex(function callbackFn(element, index, array) { ... }, thisArg)

### Parameters

`callbackFn`  
A function to execute on each value in the array until the function returns `true`, indicating that the satisfying element was found.

It takes three arguments:

`element`  
The current element being processed in the array.

 `index` <span class="badge inline optional">Optional</span>   
The index of the current element being processed in the array.

 `array` <span class="badge inline optional">Optional</span>   
The array `findIndex()` was called upon.

 `thisArg` <span class="badge inline optional">Optional</span>   
Optional object to use as `this` when executing `callbackFn`.

### Return value

The index of the first element in the array that passes the test. Otherwise, `-1`.

Note: if the index of the first element in the array that passes the test is `0`, the return value of `findIndex` will be interpreted as [Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) in conditional statements.

Description
-----------

The `findIndex()` method executes the `callbackFn` function once for every index in the array until it finds the one where `callbackFn` returns a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value.

If such an element is found, `findIndex()` immediately returns the element's index. If `callbackFn` never returns a truthy value (or the array's `length` is `0`), `findIndex()` returns `-1`.

**Note:** Unlike other array methods such as [`Array.some()`](some), `callbackFn` is run even for indexes with unassigned values.

`callbackFn` is invoked with three arguments:

1.  The value of the element
2.  The index of the element
3.  The Array object being traversed

If a `thisArg` parameter is passed to `findIndex()`, it will be used as the `this` inside each invocation of the `callbackFn`. If it is not provided, then [`undefined`](../undefined) is used.

The range of elements processed by `findIndex()` is set before the first invocation of `callbackFn`. `callbackFn` will not process the elements appended to the array after the call to `findIndex()` begins. If an existing, unvisited element of the array is changed by `callbackFn`, its value passed to the `callbackFn` will be the value at the time `findIndex()` visits the element's index.

Elements that are [`deleted`](../../operators/delete) are still visited.

Examples
--------

### Find the index of a prime number in an array

The following example returns the index of the first element in the array that is a prime number, or `-1` if there is no prime number.

    function isPrime(num) {
      for (let i = 2; num > i; i++) {
        if (num % i == 0) {
          return false;
        }
      }
      return num > 1;
    }

    console.log([4, 6, 8, 9, 12].findIndex(isPrime)); // -1, not found
    console.log([4, 6, 7, 9, 12].findIndex(isPrime)); // 2 (array[2] is 7)

### Find index using arrow function

The following example finds the index of a fruit using an arrow function:

    const fruits = ["apple", "banana", "cantaloupe", "blueberries", "grapefruit"];

    const index = fruits.findIndex(fruit => fruit === "blueberries");

    console.log(index); // 3
    console.log(fruits[index]); // blueberries

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.findindex">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype.findindex</span></a></td></tr></tbody></table>

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

`findIndex`

45

12

25

No

32

8

45

45

4

32

8

5.0

See also
--------

-   [`Array.prototype.find()`](find)
-   [`Array.prototype.indexOf()`](indexof)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex</a>
