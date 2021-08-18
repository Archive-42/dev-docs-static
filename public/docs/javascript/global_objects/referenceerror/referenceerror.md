ReferenceError() constructor
============================

The `ReferenceError` object represents an error when a non-existent variable is referenced.

Syntax
------

    new ReferenceError()
    new ReferenceError(message)
    new ReferenceError(message, fileName)
    new ReferenceError(message, fileName, lineNumber)

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
Human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span>   
The name of the file containing the code that caused the exception.

 `lineNumber` <span class="badge inline optional">Optional</span>   
The line number of the code that caused the exception

Examples
--------

### Catching a ReferenceError

    try {
      let a = undefinedVariable
    } catch (e) {
      console.log(e instanceof ReferenceError)  // true
      console.log(e.message)                    // "undefinedVariable is not defined"
      console.log(e.name)                       // "ReferenceError"
      console.log(e.fileName)                   // "Scratchpad/1"
      console.log(e.lineNumber)                 // 2
      console.log(e.columnNumber)               // 6
      console.log(e.stack)                      // "@Scratchpad/2:2:7\n"
    }

### Creating a ReferenceError

    try {
      throw new ReferenceError('Hello', 'someFile.js', 10)
    } catch (e) {
      console.log(e instanceof ReferenceError)  // true
      console.log(e.message)                    // "Hello"
      console.log(e.name)                       // "ReferenceError"
      console.log(e.fileName)                   // "someFile.js"
      console.log(e.lineNumber)                 // 10
      console.log(e.columnNumber)               // 0
      console.log(e.stack)                      // "@Scratchpad/2:2:9\n"
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

`ReferenceError`

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

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError/ReferenceError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError/ReferenceError</a>
