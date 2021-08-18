WakeLockSentinel.onrelease
==========================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `onrelease` property of the [`WakeLockSentinel`](../wakelocksentinel) is fired when the sentinel object's handle has been released.

A [`WakeLockSentinel`](../wakelocksentinel) can be released manually via the release() method, or automatically via the platform wake lock. This can happen if the document becomes inactive or looses visibility, if the device is low on power or the user turns on a power save mode.

This interface inherits from the [`Event`](../event) interface.

Syntax
------

    wakeLockSentinel.onrelease = function(event) {...}

Examples
--------

This example updates the UI should the wake lock be released.

    wakeLock.addEventListener('release', () => {

      // if wake lock is released alter the UI accordingly

      statusElement.textContent = 'Wake Lock has been released';
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-onrelease-attribute">Screen Wake Lock API<br />
<span class="small">The definition of 'onrelease' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onrelease`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/onrelease" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/onrelease</a>
