Map.prototype.delete()
======================

The `delete()` method removes the specified element from a `Map` object by key.

Syntax
------

    delete(key)

### Parameters

`key`  
The key of the element to remove from the `Map` object.

### Return value

`true` if an element in the `Map` object existed and has been removed, or `false` if the element does not exist.

Examples
--------

### Using delete()

    var myMap = new Map();
    myMap.set('bar', 'foo');

    myMap.delete('bar'); // Returns true. Successfully removed.
    myMap.has('bar');    // Returns false. The "bar" element is no longer present.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-map.prototype.delete">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-map.prototype.delete</span></a></td></tr></tbody></table>

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

38

12

13

11

25

8

38

38

14

25

8

3.0

See also
--------

-   [`Map`](../map)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete</a>
