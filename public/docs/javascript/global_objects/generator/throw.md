Generator.prototype.throw()
===========================

The `throw()` method resumes the execution of a generator by throwing an error into it and returns an object with two properties `done` and `value`.

Syntax
------

    throw(exception)

### Parameters

`exception`  
The exception to throw. For debugging purposes, it is useful to make it an `instanceof` [`Error`](../error).

### Return value

An [`Object`](../object) with two properties:

 `done` (boolean)  
-   Has the value `true` if the iterator is past the end of the iterated sequence. In this case `value` optionally specifies the *return value* of the iterator.
-   Has the value `false` if the iterator was able to produce the next value in the sequence. This is equivalent of not specifying the `done` property altogether.

`value`  
Any JavaScript value returned by the iterator. Can be omitted when `done` is `true`.

Examples
--------

### Using throw()

The following example shows a simple generator and an error that is thrown using the `throw` method. An error can be caught by a [`try...catch`](../../statements/try...catch) block as usual.

    function* gen() {
      while(true) {
        try {
           yield 42;
        } catch(e) {
          console.log('Error caught!');
        }
      }
    }

    const g = gen();
    g.next();
    // { value: 42, done: false }
    g.throw(new Error('Something went wrong'));
    // "Error caught!"
    // { value: 42, done: false }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-generator.prototype.throw">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-generator.prototype.throw</span></a></td></tr></tbody></table>

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

`throw`

39

13

26

No

26

10

39

39

26

26

10

4.0

See also
--------

-   [`function*`](../../statements/function*)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/throw" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/throw</a>
