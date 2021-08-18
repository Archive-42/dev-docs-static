Location: password
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `password` property of the [`Location`](../location) interface is a [`USVString`](../usvstring) containing the password specified before the domain name.

If it is set without first setting the `username` property, it silently fails.

Syntax
------

    string = object.password;
    object.password = string;

Examples
--------

    // Let's <a id="myAnchor" href="https://anonymous:flabada@developer.mozilla.org/en-US/docs/location.username"> be in the document
    var anchor = document.getElementByID("myAnchor");
    var result = anchor.password; // Returns:'flabada'

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

`password`

No

No

26-45

No

No

No

No

No

26-45

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/password" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/password</a>
