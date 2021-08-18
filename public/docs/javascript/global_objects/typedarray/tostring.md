TypedArray.prototype.toString()
===============================

The `toString()` method returns a string representing the specified array and its elements. This method has the same algorithm as [`Array.prototype.toString()`](../array/tostring). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    toString()

### Return value

A string representing the elements of the typed array.

Examples
--------

The [`TypedArray`](../typedarray) objects override the `toString` method of [`Object`](../object). For `TypedArray` objects, the `toString` method joins the array and returns one string containing each typed array element separated by commas. For example, the following code creates a typed array and uses `toString` to convert the array to a string.

    var numbers = new Uint8Array([2, 5, 8, 1, 4])
    numbers.toString(); // "2,5,8,1,4"

JavaScript calls the `toString` method automatically when a typed array is to be represented as a text value or when an array is referred to in a string concatenation.

### Compatibility

If a browser doesn't support the `TypedArray.prototype.toString()` method yet, JavaScript will call the `toString` method of [`Object`](../object):

    var numbers = new Uint8Array([2, 5, 8, 1, 4])
    numbers.toString(); // "[object Uint8Array]"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

7

12

51

10

11.6

5.1

≤37

18

51

12

5

1.0

See also
--------

-   [`TypedArray.prototype.join()`](join)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toString</a>
