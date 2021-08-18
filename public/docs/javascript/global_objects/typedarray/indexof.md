TypedArray.prototype.indexOf()
==============================

The `indexOf()` method returns the first index at which a given element can be found in the typed array, or -1 if it is not present. This method has the same algorithm as [`Array.prototype.indexOf()`](../array/indexof). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    indexOf(searchElement)
    indexOf(searchElement, fromIndex)

### Parameters

`searchElement`  
Element to locate in the typed array.

 `fromIndex` <span class="badge inline optional">Optional</span>   
The index to start the search at. If the index is greater than or equal to the typed array's length, -1 is returned, which means the typed array will not be searched. If the provided index value is a negative number, it is taken as the offset from the end of the typed array. Note: if the provided index is negative, the typed array is still searched from front to back. If the calculated index is less than 0, then the whole typed array will be searched. Default: 0 (entire typed array is searched).

### Return value

The first index of the element in the array; `-1` if not found.

Description
-----------

`indexOf` compares `searchElement` to elements of the typed array using [strict equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#using_the_equality_operators) (the same method used by the ===, or triple-equals, operator).

Examples
--------

### Using indexOf

    var uint8 = new Uint8Array([2, 5, 9]);
    uint8.indexOf(2);     // 0
    uint8.indexOf(7);     // -1
    uint8.indexOf(9, 2);  // 2
    uint8.indexOf(2, -1); // -1
    uint8.indexOf(2, -3); // 0

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.indexof</span></a></td></tr></tbody></table>

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

`indexOf`

45

14

37

Starting with Firefox 47, this method will no longer return `-0`. For example, `new Uint8Array([0]).indexOf(0, -0)` will now always return `+0`.

No

32

9.1

No

45

37

Starting with Firefox 47, this method will no longer return `-0`. For example, `new Uint8Array([0]).indexOf(0, -0)` will now always return `+0`.

32

9.3

5.0

See also
--------

-   [`TypedArray.prototype.lastIndexOf()`](lastindexof)
-   [`Array.prototype.indexOf()`](../array/indexof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/indexOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/indexOf</a>
