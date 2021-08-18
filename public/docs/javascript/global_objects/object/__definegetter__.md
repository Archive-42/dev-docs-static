Object.prototype.\_\_defineGetter\_\_()
=======================================

**Warning:** This feature is deprecated in favor of defining getters using the [object initializer syntax](../../operators/object_initializer) or the [`Object.defineProperty()`](defineproperty) API. While this feature is widely implemented, it is only described in the [ECMAScript specification](https://tc39.github.io/ecma262/#sec-additional-ecmascript-features-for-web-browsers) because of legacy usage. This method should not be used since better alternatives exist.

The `__defineGetter__` method binds an object's property to a function to be called when that property is looked up.

Syntax
------

    __defineGetter__(prop, func)

### Parameters

`prop`  
A string containing the name of the property to bind to the given function.

`func`  
A function to be bound to a lookup of the specified property.

### Return value

[`undefined`](../undefined).

Description
-----------

The `__defineGetter__` allows a [getter](../../functions/get) to be defined on a pre-existing object.

Examples
--------

### Non-standard and deprecated way

    var o = {};
    o.__defineGetter__('gimmeFive', function() { return 5; });
    console.log(o.gimmeFive); // 5

### Standard-compliant ways

    // Using the get operator
    var o = { get gimmeFive() { return 5; } };
    console.log(o.gimmeFive); // 5

    // Using Object.defineProperty
    var o = {};
    Object.defineProperty(o, 'gimmeFive', {
      get: function() {
        return 5;
      }
    });
    console.log(o.gimmeFive); // 5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.prototype.__defineGetter__">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.prototype.__defineGetter__</span></a></td></tr></tbody></table>

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

`__defineGetter__`

1

12

1

Starting with Firefox 48, this method can no longer be called at the global scope without any object. A `TypeError` will be thrown otherwise. Previously, the global object was used in these cases automatically, but this is no longer the case.

11

9.5

3

1

18

4

10.1

1

1.0

See also
--------

-   [`Object.prototype.__defineSetter__()`](__definesetter__)
-   [`get`](../../functions/get) operator
-   [`Object.defineProperty()`](defineproperty)
-   [`Object.prototype.__lookupGetter__()`](__lookupgetter__)
-   [`Object.prototype.__lookupSetter__()`](__lookupsetter__)
-   [JS Guide: Defining Getters and Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#defining_getters_and_setters)
-   [\[Blog Post\] Deprecation of \_\_defineGetter\_\_ and \_\_defineSetter\_\_](https://whereswalden.com/2010/04/16/more-spidermonkey-changes-ancient-esoteric-very-rarely-used-syntax-for-creating-getters-and-setters-is-being-removed/)
-   [bug 647423](https://bugzilla.mozilla.org/show_bug.cgi?id=647423)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineGetter__" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineGetter__</a>
