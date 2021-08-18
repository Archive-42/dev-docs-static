Object.getPrototypeOf()
=======================

The `Object.getPrototypeOf()` method returns the prototype (i.e. the value of the internal `[[Prototype]]` property) of the specified object.

Syntax
------

    Object.getPrototypeOf(obj)

### Parameters

`obj`  
The object whose prototype is to be returned.

### Return value

The prototype of the given object. If there are no inherited properties, [`null`](../null) is returned.

Examples
--------

### Using getPrototypeOf

    var proto = {};
    var obj = Object.create(proto);
    Object.getPrototypeOf(obj) === proto; // true

### Non-object coercion

In ES5, it will throw a [`TypeError`](../typeerror) exception if the obj parameter isn't an object. In ES2015, the parameter will be coerced to an [`Object`](../object).

    Object.getPrototypeOf('foo');
    // TypeError: "foo" is not an object (ES5 code)
    Object.getPrototypeOf('foo');
    // String.prototype                  (ES2015 code)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.getprototypeof">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.getprototypeof</span></a></td></tr></tbody></table>

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

`getPrototypeOf`

5

12

3.5

9

12.1

5

1

18

4

12.1

5

1.0

### Opera-specific notes

Even though older Opera versions don't support `Object.getPrototypeOf()` yet, Opera supports the non-standard [`__proto__`](proto) property since Opera 10.50.

See also
--------

-   [`Object.prototype.isPrototypeOf()`](isprototypeof)
-   [`Object.setPrototypeOf()`](setprototypeof)
-   [`Object/proto`](proto)
-   John Resig's post on [getPrototypeOf](http://ejohn.org/blog/objectgetprototypeof/)
-   [`Reflect.getPrototypeOf()`](../reflect/getprototypeof)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf</a>
