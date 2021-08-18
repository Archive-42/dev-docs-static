Error() constructor
===================

The `Error` constructor creates an error object.

Syntax
------

    new Error()
    new Error(message)
    new Error(message, fileName)
    new Error(message, fileName, lineNumber)

### Parameters

 `message`<span class="badge inline optional">Optional</span>   
A human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The value for the `fileName` property on the created `Error` object. Defaults to the name of the file containing the code that called the `Error()` constructor.

 `lineNumber` <span class="badge inline optional">Optional</span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The value for the `lineNumber` property on the created `Error` object. Defaults to the line number containing the `Error()` constructor invocation.

Examples
--------

### Function call or new construction

When `Error` is used like a function -- without [`new`](../../operators/new), it will return an `Error` object. Therefore, a mere call to `Error` will produce the same output that constructing an `Error` object via the `new` keyword would.

    // this...
    const x = Error('I was created using a function call!')

    // ...has the same functionality as this.
    const y = new Error('I was constructed via the "new" keyword!')

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-error-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-error-constructor</span></a></td></tr></tbody></table>

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

`Error`

1

12

1

6

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [`throw`](../../statements/throw)
-   [`try...catch`](../../statements/try...catch)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/Error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/Error</a>
