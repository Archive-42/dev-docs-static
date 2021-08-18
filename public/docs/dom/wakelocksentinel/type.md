WakeLockSentinel.type
=====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only `type` property of the [`WakeLockSentinel`](../wakelocksentinel) interface returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the currently acquired [`WakeLockSentinel`](../wakelocksentinel) type.

Syntax
------

    var type = sentinel.type;

### Value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the currently acquired wake lock type.

 *type* <span class="badge inline readonly">Read only </span>   
Return values are:

-   `'screen'`: A screen wake lock. Prevents devices from dimming or locking the screen.

Examples
--------

This example shows an asynchronous function that acquires a [`WakeLockSentinel`](../wakelocksentinel), then logs the type to the console.

    const requestWakeLock = async () => {
      wakeLock = await navigator.wakeLock.request('screen');
      console.log(wakeLock.type); // logs 'screen'
    };

    requestWakeLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-wakelocktype-enum">Screen Wake Lock API<br />
<span class="small">The definition of 'WakeLockType' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/type</a>
