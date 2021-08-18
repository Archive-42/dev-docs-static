Function.prototype.toSource()
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `toSource()` method returns a string representing the source code of the object. This method is usually called internally by JavaScript and not explicitly in code. You can call `toSource()` while debugging to examine the contents of an object.

Syntax
------

    toSource()

### Return value

A string representing the source code of the object.

Examples
--------

### Native functions

For the built-in [`Function`](../function) object, `toSource()` returns the following string indicating that the source code is not available:

    function Function() {
      [native code]
    }

### Custom functions

For custom functions, `toSource()` returns the JavaScript source that defines the object as a string.

    // For example:
    function hello() {
      console.log("Hello, World!");
    }

    hello.toSource();

    // Results in:
    "function hello() {
        console.log(\"Hello, World!\");
    }"

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

1-74

Starting in Firefox 74, `toSource()` is no longer available for use by web content. It is still allowed for internal and privileged code.

No

No

No

No

No

4

No

No

No

See also
--------

-   [`Object.prototype.toSource()`](../object/tosource)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toSource</a>
