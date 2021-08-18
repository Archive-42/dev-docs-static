String.prototype.sub()
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `sub()` method creates a [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub) HTML element that causes a string to be displayed as subscript.

Syntax
------

    sub()

### Return value

A string containing a [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub) HTML element.

Description
-----------

The `sub()` method embeds a string in a `<sub>` element: "`<sub>str</sub>`".

Examples
--------

### Using sub() and sup() methods

The following example uses the `sub()` and [`sup()`](sup) methods to format a string:

    var superText = 'superscript';
    var subText = 'subscript';

    console.log('This is what a ' + superText.sup() + ' looks like.');
    // "This is what a <sup>superscript</sup> looks like."

    console.log('This is what a ' + subText.sub() + ' looks like.');
    // "This is what a <sub>subscript</sub> looks like."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-string.prototype.sub">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-string.prototype.sub</span></a></td></tr></tbody></table>

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

`sub`

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

-   [`String.prototype.sup()`](sup)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sub" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sub</a>
