Error.prototype.toSource()
==========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `toSource()` method returns code that could eval to the same error.

Syntax
------

    toSource()

### Return value

A string containing the source code of the error.

Examples
--------

### Using toSource

Calling the `toSource` method of an [`Error`](../error) instance (including *[NativeErrors](../error#error_types)*) will return a string containing the source code of the error. This string can be evaluated to create an (approximately) equal object. Naturally, the string containing the source follows the structure of the [`Error`](../error) constructor. For example:

    (newname(message ,fileName,lineNumber))

where these attributes correspond to the respective properties of the error instance.

**Note:** Be aware that the properties used by the `toSource` method in the creation of this string are mutable and may not accurately reflect the function used to create an error instance or the filename or line number where the actual error occurred.

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

`toSource`

No

No

1-74

Starting in Firefox 74, `toSource()` is no longer available for use by web content. It is still allowed for internal and privileged code.

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

-   [`Error.prototype.fileName`](filename)
-   [`Error.prototype.lineNumber`](linenumber)
-   [`Error.prototype.message`](message)
-   [`Error.prototype.name`](name)
-   [`Object.prototype.toSource()`](../object/tosource)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/toSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/toSource</a>
