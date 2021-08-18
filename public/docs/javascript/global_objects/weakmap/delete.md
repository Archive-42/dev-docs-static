WeakMap.prototype.delete()
==========================

The `delete()` method removes the specified element from a [`WeakMap`](../weakmap) object.

Syntax
------

    delete(key)

### Parameters

`key`  
The key of the element to remove from the `WeakMap` object.

### Return value

`true` if an element in the `WeakMap` object has been removed successfully. `false` if the key is not found in the `WeakMap` or if the key is not an object.

Examples
--------

### Using the delete() method

    var wm = new WeakMap();
    wm.set(window, 'foo');

    wm.delete(window); // Returns true. Successfully removed.

    wm.has(window);    // Returns false. The window object is no longer in the WeakMap.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakmap.prototype.delete">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakmap.prototype.delete</span></a></td></tr></tbody></table>

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

`delete`

36

12

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. This has been fixed in version 38 and later to return `false` as per the ES2015 standard.

11

23

8

37

36

6

Prior to Firefox 38, this method threw a `TypeError` when the key parameter was not an object. This has been fixed in version 38 and later to return `false` as per the ES2015 standard.

24

8

3.0

See also
--------

-   [`WeakMap`](../weakmap)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/delete</a>
