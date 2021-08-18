WakeLock.request()
==================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `request()` method of the [`WakeLock`](../wakelock) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`WakeLockSentinel`](../wakelocksentinel) object, which allows control over screen dimming and locking.

Syntax
------

    var wakeLock = navigator.wakeLock.request(type);

### Parameters

*type*  
Options are as follows:

-   `'screen'`: Requests a screen wake lock. Prevents devices from dimming or locking the screen.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`WakeLockSentinel`](../wakelocksentinel) object.

### Exceptions

`NotAllowedError`  
Thrown when wake lock is not available, which can happen because:

-   Document is not allowed to use screen wake lock due to screen-wake-lock policy.
-   Document is not fully active.
-   Document is hidden.
-   [User Agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) could not acquire platform's wake lock.

Examples
--------

The following asynchronous function requests a [`WakeLockSentinel`](../wakelocksentinel) object. The `request()` method is wrapped in a `try...catch` statement to account for if the browser refuses the request for any reason.

    const requestWakeLock = async () => {
      try {

        const wakeLock = await navigator.wakeLock.request('screen');

      } catch (err) {
        // The wake lock request fails - usually system-related, such as low battery.

        console.log(`${err.name}, ${err.message}`);
      }
    }

    requestWakeLock();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-request-method">Screen Wake Lock API<br />
<span class="small">The definition of 'request()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`WakeLock`](../wakelock)
-   [`Navigator.wakeLock`](../navigator/wakelock)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLock/request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLock/request</a>
