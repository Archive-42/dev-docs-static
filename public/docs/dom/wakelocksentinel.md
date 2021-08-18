WakeLockSentinel
================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `WakeLockSentinel` interface of the [`Screen Wake Lock API`](screen_wake_lock_api) provides a handle to the underlying platform wake lock and can be manually released and reacquired. An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) representing the wake lock is returned via the [`navigator.wakelock.request()`](wakelock/request) method.

An acquired `WakeLockSentinel` can be released manually via the [`release()`](wakelocksentinel/release) method, or automatically via the platform wake lock. This can happen if the document becomes inactive or looses visibility, if the device is low on power or the user turns on a power save mode. Releasing all `WakeLockSentinel` instances of a given wake lock type will cause the underlying platform wake lock to be released.

Properties
----------

*This interface provides the following properties.*

 [`released`](wakelocksentinel/released) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the `WakeLockSentinel` has been released.

 [`type`](wakelocksentinel/type) <span class="badge inline readonly">Read only </span>   
Returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representation of the currently acquired `WakeLockSentinel` type.  
Return values are:

-   `'screen'`: A screen wake lock. Prevents devices from dimming or locking the screen.

Event handlers
--------------

[`onrelease`](wakelocksentinel/onrelease)  
Fired when the [`release()`](wakelocksentinel/release) method is called or the wake lock is released by the user agent.

Methods
-------

[`release()`](wakelocksentinel/release)  
Releases the `WakeLockSentinel`, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that is resolved once the sentinel has been successfully released.

Examples
--------

In this example we create an asynchronous function which requests a `WakeLockSentinel`. Once acquired we listen for the `onrelease` event which can be used to give appropriate UI feedback. The sentinel can be acquired or released via appropriate interactions.

    // create a reference for the wake lock
    let wakeLock = null;

    // create an async function to request a wake lock
    const requestWakeLock = async () => {
      try {
        wakeLock = await navigator.wakeLock.request('screen');

        // listen for our release event
        wakeLock.addEventListener('release', () => {
          // if wake lock is released alter the UI accordingly
        });

      } catch (err) {
        // if wake lock request fails - usually system related, such as battery

      }
    }

    wakeLockOnButton.addEventListener('click', () => {
      requestWakeLock();
    })

    wakeLockOffButton.addEventListener('click', () => {
      if (wakeLock !== null) {
        wakeLock.release()
          .then(() => {
            wakeLock = null;
          })
      }
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/#the-wakelocksentinel-interface">Screen Wake Lock API<br />
<span class="small">The definition of 'WakeLockSentinel' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WakeLockSentinel`

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

`released`

87

87

No

No

Yes

No

87

87

No

Yes

No

14.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WakeLockSentinel</a>
