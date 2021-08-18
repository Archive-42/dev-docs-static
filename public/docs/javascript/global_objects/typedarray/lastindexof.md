TypedArray.prototype.lastIndexOf()
==================================

The `lastIndexOf()` method returns the last index at which a given element can be found in the typed array, or -1 if it is not present. The typed array is searched backwards, starting at `fromIndex`. This method has the same algorithm as [`Array.prototype.lastIndexOf()`](../array/lastindexof). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    lastIndexOf(searchElement)
    lastIndexOf(searchElement, fromIndex)

### Parameters

`searchElement`  
Element to locate in the typed array.

`fromIndex`  
Optional. The index at which to start searching backwards. Defaults to the typed array's length, i.e. the whole typed array will be searched. If the index is greater than or equal to the length of the typed array, the whole typed array will be searched. If negative, it is taken as the offset from the end of the typed array. Note that even when the index is negative, the typed array is still searched from back to front. If the calculated index is less than 0, -1 is returned, i.e. the typed array will not be searched.

### Return value

The last index of the element in the array; `-1` if not found.

Description
-----------

`lastIndexOf` compares `searchElement` to elements of the typed array using [strict equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#using_the_equality_operators) (the same method used by the ===, or triple-equals, operator).

Examples
--------

### Using lastIndexOf

    var uint8 = new Uint8Array([2, 5, 9, 2]);
    uint8.lastIndexOf(2);     // 3
    uint8.lastIndexOf(7);     // -1
    uint8.lastIndexOf(2, 3);  // 3
    uint8.lastIndexOf(2, 2);  // 0
    uint8.lastIndexOf(2, -2); // 0
    uint8.lastIndexOf(2, -1); // 3

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.lastindexof</span></a></td></tr></tbody></table>

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

`lastIndexOf`

45

14

37

Starting with Firefox 47, this method will no longer return `-0`. For example, `new Uint8Array([0]).lastIndexOf(0, -0)` will now always return `+0`.

No

32

10

45

45

37

Starting with Firefox 47, this method will no longer return `-0`. For example, `new Uint8Array([0]).lastIndexOf(0, -0)` will now always return `+0`.

32

10

5.0

See also
--------

-   [`TypedArray.prototype.indexOf()`](indexof)
-   [`Array.prototype.lastIndexOf()`](../array/lastindexof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/lastIndexOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/lastIndexOf</a>
