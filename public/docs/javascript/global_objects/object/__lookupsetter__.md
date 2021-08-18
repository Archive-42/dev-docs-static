Object.prototype.\_\_lookupSetter\_\_()
=======================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `__lookupSetter__` method returns the function bound as a setter to the specified property.

Syntax
------

    __lookupSetter__(sprop)

### Parameters

`sprop`  
A string containing the name of the property whose setter should be returned.

### Return value

The function bound as a setter to the specified property.

Description
-----------

If a setter has been defined for an object's property, it was not possible to reference the setter function through that property, because that property refers to the return value of that function. `__lookupSetter__` can be used to obtain a reference to the setter function.

It is now possible to do this in a standardized way using [`Object.getOwnPropertyDescriptor()`](getownpropertydescriptor).

Examples
--------

### Standard-compliant and non-standard ways to get a property setter

    var obj = {
      set foo(value) {
        this.bar = value;
      }
    };

    // Non-standard and deprecated way
    obj.__lookupSetter__('foo')
    // (function(value) { this.bar = value; })

    // Standard-compliant way
    Object.getOwnPropertyDescriptor(obj, 'foo').set;
    // (function(value) { this.bar = value; })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-object.prototype.__lookupSetter__">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-object.prototype.__lookupSetter__</span></a></td></tr></tbody></table>

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

`__lookupSetter__`

1

12

1

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

-   [`Object.prototype.__lookupGetter__()`](__lookupgetter__)
-   [`set`](../../functions/set) operator
-   [`Object.getOwnPropertyDescriptor()`](getownpropertydescriptor) and [`Object.getPrototypeOf()`](getprototypeof)
-   [`Object.prototype.__defineGetter__()`](__definegetter__)
-   [`Object.prototype.__defineSetter__()`](__definesetter__)
-   [JS Guide: Defining Getters and Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects#defining_getters_and_setters)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__lookupSetter__" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__lookupSetter__</a>
