Symbol.prototype.toSource()
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `toSource()` method returns a string representing the source code of the object.

This method is usually called internally by JavaScript.

Syntax
------

    toSource()

### Return value

A string representing the source code of the object.

Examples
--------

### Native function

For the built-in `Symbol` object, `toSource` returns the following string indicating that the source code is not available:

    "function Symbol() {
       [native code]
    }"

For instances of `Symbol`, `toSource` returns a string representing the source code.

    "Symbol()"

Specifications
--------------

Not part of any standard.

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

`toSource`

No

No

36-74

Starting in Firefox 74, `toSource()` is no longer available for use by web content. It is still allowed for internal and privileged code.

No

No

No

No

No

36

No

No

No

See also
--------

-   [`Object.prototype.toSource()`](../object/tosource)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toSource</a>
