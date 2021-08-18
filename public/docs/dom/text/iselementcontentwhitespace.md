Text.isElementContentWhitespace
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** You may replace it with `/\s+/.test(Text.data)`, `/\s+/.test(Text.nodeValue)`, or `/\s+/.test(Text.textContent)`. Putting any property that represents the textual content of the `Text` node into `test()` should do the same work just like the three example above.

The `Text.isElementContentWhitespace` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating whether or not the text node's content consists solely of whitespace.

Syntax
------

    b = textnode.isElementContentWhitespace;

Example
-------

In the example below, we create a node with mixed display and whitespace characters and the attribute is `false`.

    var tn = document.createTextNode("Hello world");
    tn.isElementContentWhitespace; /* evaluates to false */

For a node that is all whitespace characters, the `isElementContentWhitespace` evaluates to true.

    var ws = document.createTextNode("  \t \r\n   ")
    ws.isElementContentWhitespace; /* evaluates to true */

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

`isElementContentWhitespace`

No

No

Yes-10

No

No

No

No

No

Yes-10

No

No

No

See also
--------

-   The [`Text`](../text) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Text/isElementContentWhitespace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Text/isElementContentWhitespace</a>
