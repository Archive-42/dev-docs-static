EvalError() constructor
=======================

The `EvalError` constructor creates a new error regarding the global [`eval()`](../eval) function. This exception is not thrown by JavaScript anymore, however the `EvalError` object remains for compatibility.

Syntax
------

    new EvalError()
    new EvalError(message)
    new EvalError(message, fileName)
    new EvalError(message, fileName, lineNumber)

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
Human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span>   
The name of the file containing the code that caused the exception

 `lineNumber` <span class="badge inline optional">Optional</span>   
The line number of the code that caused the exception

Examples
--------

`EvalError` is not used in the current ECMAScript specification and will thus not be thrown by the runtime. However, the object itself remains for backwards compatibility with earlier versions of the specification.

### Creating an EvalError

    try {
      throw new EvalError('Hello', 'someFile.js', 10);
    } catch (e) {
      console.log(e instanceof EvalError); // true
      console.log(e.message);              // "Hello"
      console.log(e.name);                 // "EvalError"
      console.log(e.fileName);             // "someFile.js"
      console.log(e.lineNumber);           // 10
      console.log(e.columnNumber);         // 0
      console.log(e.stack);                // "@Scratchpad/2:2:9\n"
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-nativeerror-constructors">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-nativeerror-constructors</span></a></td></tr></tbody></table>

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

`EvalError`

1

12

1

5.5

5

1

1

18

4

10.1

1

1.0

See also
--------

-   [`Error`](../error)
-   [`eval()`](../eval)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError/EvalError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError/EvalError</a>
