Object() constructor
====================

The `Object` creates an object wrapper for the given value.

-   If the value is [`null`](../null) or [`undefined`](../undefined), it will create and return an empty object.
-   Otherwise, it will return an object of a Type that corresponds to the given value.
-   If the value is an object already, it will return the value.

When called in a non-constructor context, `Object` behaves identically to `new Object()`.

Syntax
------

    new Object()
    new Object(value)

### Parameters

`value`  
Any value.

Examples
--------

### Creating a new Object

    let o = new Object()
    o.foo = 42

    console.log(o)
    // Object { foo: 42 }

### Using Object given undefined and null types

The following examples store an empty `Object` object in `o`:

    let o = new Object()

    let o = new Object(undefined)

    let o = new Object(null)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object-constructor</span></a></td></tr></tbody></table>

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

`Object`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [Object initializer](../../operators/object_initializer)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/Object" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/Object</a>
