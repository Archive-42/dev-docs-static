Object.values()
===============

The `Object.values()` method returns an array of a given object's own enumerable property values, in the same order as that provided by a [`for...in`](../../statements/for...in) loop. (The only difference is that a `for...in` loop enumerates properties in the prototype chain as well.)

Syntax
------

    Object.values(obj)

### Parameters

`obj`  
The object whose enumerable own property values are to be returned.

### Return value

An array containing the given object's own enumerable property values.

Description
-----------

`Object.values()` returns an array whose elements are the enumerable property values found on the object. The ordering of the properties is the same as that given by looping over the property values of the object manually.

Polyfill
--------

To add compatible `Object.values` support in older environments that do not natively support it, you can find a Polyfill in the [tc39/proposal-object-values-entries](https://github.com/tc39/proposal-object-values-entries) or in the [es-shims/Object.values](https://github.com/es-shims/Object.values) repositories.

Examples
--------

### Using Object.values

    const obj = { foo: 'bar', baz: 42 };
    console.log(Object.values(obj)); // ['bar', 42]

    // Array-like object
    const arrayLikeObj1 = { 0: 'a', 1: 'b', 2: 'c' };
    console.log(Object.values(arrayLikeObj1 )); // ['a', 'b', 'c']

    // Array-like object with random key ordering
    // When using numeric keys, the values are returned in the keys' numerical order
    const arrayLikeObj2 = { 100: 'a', 2: 'b', 7: 'c' };
    console.log(Object.values(arrayLikeObj2 )); // ['b', 'c', 'a']

    // getFoo is property which isn't enumerable
    const my_obj = Object.create({}, { getFoo: { value: function() { return this.foo; } } });
    my_obj.foo = 'bar';
    console.log(Object.values(my_obj)); // ['bar']

    // non-object argument will be coerced to an object
    console.log(Object.values('foo')); // ['f', 'o', 'o']

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.values">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.values</span></a></td></tr></tbody></table>

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

`values`

54

14

47

No

41

10.1

54

54

47

41

10.3

6.0

See also
--------

-   [Enumerability and ownership of properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.keys()`](keys)
-   [`Object.entries()`](entries)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values</a>
