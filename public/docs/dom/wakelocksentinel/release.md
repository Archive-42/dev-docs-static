WakeLockSentinel.release()
==========================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `release()` method of the [`WakeLockSentinel`](../wakelocksentinel) interface releases the [`WakeLockSentinel`](../wakelocksentinel), returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that is resolved once the sentinel has been successfully released.

Syntax
------

    WakeLockSentinel.release().then(...);

### Parameters

None.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`

### Exceptions

No exceptions are thrown. You should always listen for the <span class="page-not-created">`onrelease`</span> event to check if a wake lock has been released.

Examples
--------

In this example, when a user clicks a button the [`WakeLockSentinel`](../wakelocksentinel) is released.

    wakeLockOffButton.addEventListener('click', () => {
      WakeLockSentinel.release();
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-release-method">Screen Wake Lock API<br />
<span class="small">The definition of 'release()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`release`

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

-   [`WakeLockSentinel`](../wakelocksentinel)
-   [`navigator.wakeLock.request()`](../wakelock/request)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/release" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel/release</a>
