Generator.prototype.return()
============================

The `return()` method returns the given value and finishes the generator.

Syntax
------

    return(value)

### Parameters

`value`  
The value to return.

### Return value

The value that is given as an argument.

Examples
--------

### Using return()

The following example shows a simple generator and the `return` method.

    function* gen() {
      yield 1;
      yield 2;
      yield 3;
    }

    const g = gen();

    g.next();        // { value: 1, done: false }
    g.return('foo'); // { value: "foo", done: true }
    g.next();        // { value: undefined, done: true }

If `return(value)` is called on a generator that is already in "completed" state, the generator will remain in "completed" state.

If no argument is provided, the `value` property of the returned object will be "`undefined`". If an argument is provided, it will be set to the value of the `value` property of the returned object.

    function* gen() {
      yield 1;
      yield 2;
      yield 3;
    }

    const g = gen();
    g.next(); // { value: 1, done: false }
    g.next(); // { value: 2, done: false }
    g.next(); // { value: 3, done: false }
    g.next(); // { value: undefined, done: true }
    g.return(); // { value: undefined, done: true }
    g.return(1); // { value: 1, done: true }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-generator.prototype.return">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-generator.prototype.return</span></a></td></tr></tbody></table>

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

`return`

50

13

38

No

37

10

50

50

38

37

10

5.0

See also
--------

-   [`function*`](../../statements/function*)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/return" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/return</a>
