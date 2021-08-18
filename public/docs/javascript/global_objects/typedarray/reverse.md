TypedArray.prototype.reverse()
==============================

The `reverse()` method reverses a typed array in place. The first typed array element becomes the last and the last becomes the first. This method has the same algorithm as [`Array.prototype.reverse()`](../array/reverse). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    reverse()

### Return value

The reversed array.

Examples
--------

### Using reverse

    var uint8 = new Uint8Array([1, 2, 3]);
    uint8.reverse();

    console.log(uint8); // Uint8Array [3, 2, 1]

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.reverse</span></a></td></tr></tbody></table>

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

`reverse`

45

14

37

No

32

10

45

45

37

No

10

5.0

See also
--------

-   [`Array.prototype.reverse()`](../array/reverse)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reverse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reverse</a>
