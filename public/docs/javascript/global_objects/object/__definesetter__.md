Object.prototype.\_\_defineSetter\_\_()
=======================================

**Warning:** This feature is deprecated in favor of defining setters using the [object initializer syntax](../../operators/object_initializer) or the [`Object.defineProperty()`](defineproperty) API.

However, as it is widely implemented and used on the Web, it is very unlikely that browsers will stop implementing it.

The `__defineSetter__` method binds an object's property to a function to be called when an attempt is made to set that property.

Syntax
------

    __defineSetter__(prop, fun)

### Parameters

`prop`  
A string containing the name of the property to be bound to the given function.

`fun`  
A function to be called when there is an attempt to set the specified property. This function takes the form

    function(val) { . . . }

`val`  
An alias for the variable that holds the value attempted to be assigned to `prop`.

### Return value

[`undefined`](../undefined).

Description
-----------

The `__defineSetter__` method allows a [setter](../../functions/set) to be defined on a pre-existing object.

Examples
--------

### Non-standard and deprecated way

    var o = {};
    o.__defineSetter__('value', function(val) { this.anotherValue = val; });
    o.value = 5;
    console.log(o.value); // undefined
    console.log(o.anotherValue); // 5

### Standard-compliant ways

    // Using the set operator
    var o = { set value(val) { this.anotherValue = val; } };
    o.value = 5;
    console.log(o.value); // undefined
    console.log(o.anotherValue); // 5

    // Using Object.defineProperty
    var o = {};
    Object.defineProperty(o, 'value', {
      set: function(val) {
        this.anotherValue = val;
      }
    });
    o.value = 5;
    console.log(o.value); // undefined
    console.log(o.anotherValue); // 5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.prototype.__defineSetter__">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.prototype.__defineSetter__</span></a></td></tr></tbody></table>

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

`__defineSetter__`

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

-   [`Object.prototype.__defineGetter__()`](__definegetter__)
-   [`set`](../../functions/set) operator
-   [`Object.defineProperty()`](defineproperty)
-   [`Object.prototype.__lookupGetter__()`](__lookupgetter__)
-   [`Object.prototype.__lookupSetter__()`](__lookupsetter__)
-   [JS Guide: Defining Getters and Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#defining_getters_and_setters)
-   [\[Blog Post\] Deprecation of \_\_defineGetter\_\_ and \_\_defineSetter\_\_](https://whereswalden.com/2010/04/16/more-spidermonkey-changes-ancient-esoteric-very-rarely-used-syntax-for-creating-getters-and-setters-is-being-removed/)
-   [bug 647423](https://bugzilla.mozilla.org/show_bug.cgi?id=647423)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineSetter__" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineSetter__</a>
