Promise() constructor
=====================

The `Promise` constructor is primarily used to wrap functions that do not already support promises.

Syntax
------

    new Promise(executor)

### Parameters

`executor`  
A [`function`](../function) to be executed by the constructor, during the process of constructing the new `Promise` object. The `executor` is custom code that ties an outcome to a promise. You, the programmer, write the `executor`. The signature of this function is expected to be:

    function(resolutionFunc, rejectionFunc){
        // typically, some asynchronous operation.
    }

At the time when the constructor generates the new `Promise` object, it also generates a corresponding pair of functions for `resolutionFunc` and `rejectionFunc`; these are "tethered" to the `Promise` object. Therefore, the code within the `executor` has the opportunity to perform some operation and then reflect the operation's outcome (If the value is not another Promise object) as either "fulfilled" or "rejected" by terminating with an invocation of either the `resolutionFunc` or the `rejectionFunc`, respectively.

The `executor` has no meaningful return value. It communicates via the side-effect caused by `resolutionFunc` or `rejectionFunc`. The side-effect is that the `Promise` object becomes "resolved."

Typically, it works like this: The operation within `executor` is asynchronous and provides a callback. The callback is defined within the `executor` code. The callback terminates by invoking `resolutionFunc`. The invocation of `resolutionFunc` includes a `value` parameter. The `value` is passed back to the tethered `Promise` object. The `Promise` object (asynchronously) invokes any `.then()` associated with it. The `value` received by `.then()` is passed to the invocation of `handleFulfilled` as an input parameter (See "Chained Promises" section).

The `executor` might also include a `try{} catch()` block that invokes `rejectionFunc` upon error.

The signatures of these two functions are simple, they accept a single parameter of any type. Of course, the actual names of these functions can be whatever is desired, i.e. they are named as the parameters of `executor`. Each function is used by calling it when appropriate.

    resolutionFunc(value) // call on fulfilled
    rejectionFunc(reason) // call on rejected

The returned `value` can be another promise object, in which case the promise gets dynamically inserted into the chain.

### Return value

When called via `new`, the `Promise` constructor returns a promise object. The promise object will become "resolved" when either of the functions `resolutionFunc` or `rejectionFunc` are invoked. Note that if you call `resolutionFunc` or `rejectionFunc` and pass another Promise object as an argument, you can say that it is "resolved", but still cannot be said to be "settled".

Examples
--------

### Creating a new Promise

A `Promise` object is created using the `new` keyword and its constructor. This constructor takes a function, called the "executor function", as its parameter. This function should take two functions as parameters. The first of these functions (`resolve`) is called when the asynchronous task completes successfully and returns the results of the task as a value. The second (`reject`) is called when the task fails, and returns the reason for failure, which is typically an error object.

    const myFirstPromise = new Promise((resolve, reject) => {
      // do something asynchronous which eventually calls either:
      //
      //   resolve(someValue)        // fulfilled
      // or
      //   reject("failure reason")  // rejected
    });

### Making functions return a Promise

To provide a function with promise functionality, have it return a promise:

    function myAsyncFunction(url) {
      return new Promise((resolve, reject) => {
        const xhr = new XMLHttpRequest()
        xhr.open("GET", url)
        xhr.onload = () => resolve(xhr.responseText)
        xhr.onerror = () => reject(xhr.statusText)
        xhr.send()
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-promise-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-promise-constructor</span></a></td></tr></tbody></table>

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

`Promise`

32

12

29

Constructor requires a new operator since version 37.

No

19

8

Constructor requires a new operator since version 10.

4.4.3

32

29

Constructor requires a new operator since version 37.

19

8

Constructor requires a new operator since version 10.

2.0

See also
--------

-   [Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/Promise" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/Promise</a>
