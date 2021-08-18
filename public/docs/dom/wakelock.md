WakeLock
========

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `WakeLock` interface of the [`Screen Wake Lock API`](screen_wake_lock_api) prevents device screens from dimming or locking when an application needs to keep running.

The system wake lock is exposed through the global [`Navigator.wakelock`](navigator/wakelock) property.

Methods
-------

`request`  
Requests a [`WakeLockSentinel`](wakelocksentinel) object, which returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`WakeLockSentinel`](wakelocksentinel) object.

Examples
--------

The following asynchronous function requests a [`WakeLockSentinel`](wakelocksentinel) object. The [`WakeLock.request`](wakelock/request) method is wrapped in a `try...catch` statement to account for if the browser refuses the request for any reason.

    try {
      const wakeLock = await navigator.wakeLock.request('screen');
    } catch (err) {
      // the wake lock request fails - usually system related, such being low on battery
      console.log(`${err.name}, ${err.message}`);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-wakelock-interface">Screen Wake Lock API<br />
<span class="small">The definition of 'WakeLock' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WakeLock`

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

`request`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLock</a>
