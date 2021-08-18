AggregateError() constructor
============================

The `AggregateError()` constructor creates an error for several errors that need to be wrapped in a single error.

Syntax
------

    new AggregateError(errors)
    new AggregateError(errors, message)

### Parameters

`errors`  
An iterable of errors, may not actually be [`Error`](../error) instances.

 `message`<span class="badge inline optional">Optional</span>   
An optional human-readable description of the aggregate error.

Examples
--------

### Creating an `AggregateError`

    try {
      throw new AggregateError([
        new Error("some error"),
      ], 'Hello');
    } catch (e) {
      console.log(e instanceof AggregateError); // true
      console.log(e.message);                   // "Hello"
      console.log(e.name);                      // "AggregateError"
      console.log(e.errors);                    // [ Error: "some error" ]
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-aggregate-error-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-aggregate-error-constructor</span></a></td></tr></tbody></table>

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

`AggregateError`

85

85

79

No

No

14

85

85

79

No

14

No

See also
--------

-   [`Promise.any`](../promise/any)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError/AggregateError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError/AggregateError</a>
