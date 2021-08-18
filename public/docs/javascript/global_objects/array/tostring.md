Array.prototype.toString()
==========================

The `toString()` method returns a string representing the specified array and its elements.

Syntax
------

    toString()

### Return value

A string representing the elements of the array.

Description
-----------

The [`Array`](../array) object overrides the `toString` method of [`Object`](../object). For Array objects, the `toString` method joins the array and returns one string containing each array element separated by commas.

JavaScript calls the `toString` method automatically when an array is to be represented as a text value or when an array is referred to in a string concatenation.

### ECMAScript 5 semantics

Starting in JavaScript 1.8.5 (Firefox 4), and consistent with ECMAScript 5th edition semantics, the `toString()` method is generic and can be used with any object. [`Object.prototype.toString()`](../object/tostring) will be called, and the resulting value will be returned.

Examples
--------

### Using toString

    const array1 = [1, 2, 'a', '1a'];

    console.log(array1.toString());
    // expected output: "1,2,a,1a"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.tostring">ECMAScript (ECMA-262)<br />
<span class="small">The definition of 'Array.prototype.toString' in that specification.</span></a></td></tr></tbody></table>

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

1

12

1

4

4

1

≤37

18

4

10.1

1

1.0

See also
--------

-   [`Array.prototype.join()`](join)
-   [`Object.prototype.toSource()`](../object/tosource)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString</a>
