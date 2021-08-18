RangeError() constructor
========================

The `RangeError()` constructor creates an error when a value is not in the set or range of allowed values.

Syntax
------

    new RangeError()
    new RangeError(message)
    new RangeError(message, fileName)
    new RangeError(message, fileName, lineNumber)

### Parameters

 `message` <span class="badge inline optional">Optional</span>   
Human-readable description of the error.

 `fileName` <span class="badge inline optional">Optional</span>   
The name of the file containing the code that caused the exception

 `lineNumber` <span class="badge inline optional">Optional</span>   
The line number of the code that caused the exception

Examples
--------

### Using `RangeError` (for numeric values)

    function check(n)
    {
        if( !(n >= -500 && n <= 500) )
        {
            throw new RangeError("The argument must be between -500 and 500.")
        }
    }

    try
    {
        check(2000)
    }
    catch(error)
    {
        if (error instanceof RangeError)
        {
            // Handle the error
        }
    }

### Using `RangeError` (for non-numeric values)

    function check(value)
    {
        if(["apple", "banana", "carrot"].includes(value) === false)
        {
            throw new RangeError('The argument must be an "apple", "banana", or "carrot".')
        }
    }

    try
    {
        check("cabbage")
    }
    catch(error)
    {
        if(error instanceof RangeError)
        {
            // Handle the error
        }
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

`RangeError`

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
-   [`Array`](../array)
-   [`Number.toExponential()`](../number/toexponential)
-   [`Number.toFixed()`](../number/tofixed)
-   [`Number.toPrecision()`](../number/toprecision)
-   [`String.prototype.normalize()`](../string/normalize)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError/RangeError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError/RangeError</a>
