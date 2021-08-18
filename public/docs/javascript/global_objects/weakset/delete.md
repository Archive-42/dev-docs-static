WeakSet.prototype.delete()
==========================

The `delete()` method removes the specified element from a `WeakSet` object.

Syntax
------

    delete(value)

### Parameters

`value`  
Required. The object remove from the `WeakSet` object.

### Return value

`true` if an element in the `WeakSet` object has been removed successfully. `false` if the `value` is not found in the `WeakSet` or if the `value` is not an object.

Examples
--------

### Using the delete() method

    var ws = new WeakSet();
    var obj = {};

    ws.add(window);

    ws.delete(obj);    // Returns false. No obj found to be deleted.
    ws.delete(window); // Returns true.  Successfully removed.

    ws.has(window);    // Returns false. The window is no longer present in the WeakSet.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-weakset.prototype.delete">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-weakset.prototype.delete</span></a></td></tr></tbody></table>

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

34

No

23

9

37

36

34

24

9

3.0

See also
--------

-   [`WeakSet`](../weakset)
-   <span class="page-not-created">`WeakSet.prototype.clear()`</span>

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/delete</a>
