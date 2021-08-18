TypedArray.prototype.join()
===========================

The `join()` method joins all elements of an array into a string. This method has the same algorithm as [`Array.prototype.join()`](../array/join). *TypedArray* is one of the [typed array types](../typedarray#typedarray_objects) here.

Syntax
------

    join()
    join(separator)

### Parameters

 `separator` <span class="badge inline optional">Optional</span>   
Specifies a string to separate each element. The `separator` is converted to a string if necessary. If omitted, the typed array elements are separated with a comma (",").

### Return value

A string with all array elements joined.

Examples
--------

### Using join()

    var uint8 = new Uint8Array([1,2,3]);
    uint8.join();      // '1,2,3'
    uint8.join(' / '); // '1 / 2 / 3'
    uint8.join('');    // '123'

Polyfill
--------

Since there is no global object with the name *TypedArray*, polyfilling must be done on an "as needed" basis.

    // https://tc39.github.io/ecma262/#sec-%typedarray%.prototype.join
    if (!Uint8Array.prototype.join) {
      Object.defineProperty(Uint8Array.prototype, 'join', {
        value: Array.prototype.join
      });
    }

If you need to support truly obsolete JavaScript engines that don't support [`Object.defineProperty`](../object/defineproperty), it's best not to polyfill `Array.prototype` methods at all, as you can't make them non-enumerable.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.prototype.join</span></a></td></tr></tbody></table>

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

`join`

45

14

37

No

32

9.1

45

45

37

32

9.3

5.0

See also
--------

-   [`TypedArray`](../typedarray)
-   [`Array.prototype.join()`](../array/join)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/join" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/join</a>
