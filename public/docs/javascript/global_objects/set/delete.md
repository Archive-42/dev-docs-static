Set.prototype.delete()
======================

The `delete()` method removes a specified value from a `Set` object, if it is in the set.

Syntax
------

    delete(value)

### Parameters

`value`  
The value to remove from `mySet`.

### Return value

Returns `true` if `value` was already in `mySet`; otherwise `false`.

Examples
--------

### Using the delete() method

    const mySet = new Set();
    mySet.add('foo');

    mySet.delete('bar'); // Returns false. No "bar" element found to be deleted.
    mySet.delete('foo'); // Returns true. Successfully removed.

    mySet.has('foo');    // Returns false. The "foo" element is no longer present.

Let's checkout below how to delete an Object from a Set.

    const setObj = new Set();   // Create a new set.

    setObj.add({x: 10, y: 20}); // Add object in the set.

    setObj.add({x: 20, y: 30}); // Add object in the set.

    // Delete any point with `x > 10`.
    setObj.forEach(function(point){
      if (point.x > 10){
        setObj.delete(point)
      }
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-set.prototype.delete">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-set.prototype.delete</span></a></td></tr></tbody></table>

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

-   [`Set`](../set)
-   [`Set.prototype.clear()`](clear)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete</a>
