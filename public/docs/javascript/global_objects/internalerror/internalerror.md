InternalError() constructor
===========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `InternalError()` constructor creates an error that indicates an error that occurred internally in the JavaScript engine. For example: "**InternalError**: too much recursion".

Syntax
------

    new InternalError()
    new InternalError(message)
    new InternalError(message, fileName)
    new InternalError(message, fileName, lineNumber)

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
Human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span>   
The name of the file containing the code that caused the exception

 `lineNumber` <span class="badge inline optional">Optional</span>   
The line number of the code that caused the exception

Examples
--------

### Creating a new InternalError

    new InternalError("Engine failure");

Specifications
--------------

Not part of any standard.

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

`InternalError`

No

No

1

No

No

No

No

No

4

No

No

No

See also
--------

-   [`Error`](../error)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError/InternalError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError/InternalError</a>
