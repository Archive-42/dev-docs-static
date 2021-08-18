WebAssembly.RuntimeError() constructor
======================================

The `WebAssembly.RuntimeError()` constructor creates a new WebAssembly `RuntimeError` object — the type that is thrown whenever WebAssembly specifies a [trap](https://webassembly.org/docs/semantics/#traps).

Syntax
------

    new RuntimeError.LinkError()
    new RuntimeError.LinkError(message)
    new RuntimeError.LinkError(message, fileName)
    new RuntimeError.LinkError(message, fileName, lineNumber)

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
Human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span>   
The name of the file containing the code that caused the exception.

 `lineNumber` <span class="badge inline optional">Optional</span>   
The line number of the code that caused the exception.

Examples
--------

### Creating a new RuntimeError instance

The following snippet creates a new `RuntimeError` instance, and logs its details to the console:

    try {
      throw new WebAssembly.RuntimeError('Hello', 'someFile', 10);
    } catch (e) {
      console.log(e instanceof WebAssembly.RuntimeError); // true
      console.log(e.message);                             // "Hello"
      console.log(e.name);                                // "RuntimeError"
      console.log(e.fileName);                            // "someFile"
      console.log(e.lineNumber);                          // 10
      console.log(e.columnNumber);                        // 0
      console.log(e.stack);                               // returns the location where the code was run
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://webassembly.github.io/spec/js-api/#exceptiondef-runtimeerror">WebAssembly JavaScript Interface (WebAssembly JavaScript Interface)<br />
<span class="small">#exceptiondef-runtimeerror</span></a></td></tr><tr class="even"><td><a href="https://tc39.es/ecma262/#sec-nativeerror-constructors">ECMAScript Language Specification (ECMAScript)<br />
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

`RuntimeError`

57

16

52

Disabled in the Firefox 52 Extended Support Release (ESR).

No

44

11

57

57

52

Disabled in the Firefox 52 Extended Support Release (ESR).

43

11

7.0

See also
--------

-   [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) overview page
-   [WebAssembly concepts](https://developer.mozilla.org/en-US/docs/WebAssembly/Concepts)
-   [Using the WebAssembly JavaScript API](https://developer.mozilla.org/en-US/docs/WebAssembly/Using_the_JavaScript_API)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/RuntimeError/RuntimeError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/RuntimeError/RuntimeError</a>
