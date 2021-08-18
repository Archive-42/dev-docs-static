Navigator.wakeLock
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `wakeLock` read-only property returns a [`WakeLock`](../wakelock) interface which allows a document to acquire a screen wake lock. While a screen wake lock is active, the user agent will try to prevent the device from dimming the screen, turning it off completely, or showing a screensaver.

Syntax
------

    const wakeLock = navigator.wakeLock;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#extensions-to-the-navigator-interface">Screen Wake Lock API</a></td><td>Editor's Draft</td><td>Initial definition</td></tr></tbody></table>

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

`wakeLock`

84

84

No

No

Yes

No

84

84

No

Yes

No

14.0

See also
--------

-   [`WakeLock.request()`](../wakelock/request)
-   [Screen Wake Lock API](../screen_wake_lock_api)
-   [Blog post - Stay awake with the Screen Wake Lock API](https://web.dev/wakelock/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/wakeLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/wakeLock</a>
