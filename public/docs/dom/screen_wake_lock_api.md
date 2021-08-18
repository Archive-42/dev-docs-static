Screen Wake Lock API
====================

The Screen Wake Lock API provides a way to prevent devices from dimming or locking the screen when an application needs to keep running.

Concepts and Usage
------------------

Most devices by default turn off their screen after a specified amount of time to prolong the life of the hardware. Modern devices do this to save on battery power. Whilst this is a useful feature, some applications need the screen to stay awake to be their most useful.

The Screen Wake Lock API prevents the screen from turning off, dimming or locking. It allows for a simple platform-based solution which up until now could only be achieved via workarounds which were potentially power hungry. Only visible (active) documents can acquire the screen wake lock.

There are plenty of use cases for keeping a screen on, including reading an ebook, map navigation, following a recipe, presenting to an audience, scanning a QR/barcode or applications that use voice or gesture control, rather than tactile input (the default way to keep a screen awake).

You acquire a [`WakeLockSentinel`](wakelocksentinel) object by calling the [`navigator.wakeLock.request()`](wakelock/request) [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based method that resolves if the platform allows it. A request may be rejected for a number of reasons, including system settings (such as power save mode or low battery level) or if the document is not active or visible.

The sentinel is attached to the underlying system wake lock. It can be released by the system, again if the battery power is too low or the document is not active or visible. It can also be released manually via the [`WakeLockSentinel.release()`](wakelocksentinel/release) method. It is good practice to store a reference to the sentinel object to control release later and also to reacquire the lock if need be.

The Screen Wake Lock API should be used to keep the screen on to benefit usability. It's a good idea to show some feedback on the interface to show if wake lock is active and a way for the user to disable it if they wish.

Screen Wake Lock API Interfaces
-------------------------------

[`WakeLock`](wakelock)  
The `WakeLock` interface prevents device screens from dimming or locking when an application needs to keep running.

[`WakeLockSentinel`](wakelocksentinel)  
Provides a handle to the underlying platform wake lock and if referenced can be manually released and reacquired. Get an instance of the object by calling [`WakeLock.request`](wakelock/request).

[`Navigator.wakelock`](navigator/wakelock)  
Returns a [`WakeLock`](wakelock) object instance, from which all other functionality can be accessed.

Examples
--------

### Feature Detection

This code checks for wake lock support and updates the UI accordingly.

    if ('wakeLock' in navigator) {
      isSupported = true;
      statusElem.textContent = 'Screen Wake Lock API supported!';
    } else {
      wakeButton.disabled = true;
      statusElem.textContent = 'Wake lock is not supported by this browser.';
    }

### Requesting a wake lock

The following example demonstrates how to request a [`WakeLockSentinel`](wakelocksentinel) object. The [`WakeLock.request`](wakelock/request) method is [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based and so we can create an asynchronous function, which in turn updates the UI to reflect the wake lock is active.

    // Create a reference for the Wake Lock.
    let wakeLock = null;

    // create an async function to request a wake lock
    try {
      wakeLock = await navigator.wakeLock.request('screen');
      statusElem.textContent = 'Wake Lock is active!';
    } catch (err) {
      // The Wake Lock request has failed - usually system related, such as battery.
      statusElem.textContent = `${err.name}, ${err.message}`;
    }

### Releasing wake lock

The following example shows how to release the previously acquired wake lock.

    wakeLock.release()
      .then(() => {
        wakeLock = null;
      });

### Listening for wake lock release

This example updates the UI if the wake lock has been released for any reason (such as navigating away from the active window/tab).

    wakeLock.addEventListener('release', () => {
      // the wake lock has been released
      statusElem.textContent = 'Wake Lock has been released';
    });

### Reacquiring a wake lock

The following code reacquires the wake lock should the visibility of the document change and the wake lock is released.

    document.addEventListener('visibilitychange', async () => {
      if (wakeLock !== null && document.visibilityState === 'visible') {
        wakeLock = await navigator.wakeLock.request('screen');
      }
    });

### Putting it all together

You can find the [complete code on GitHub here](https://github.com/mdn/dom-examples/tree/master/screen-wake-lock-api). The [demo](https://mdn.github.io/dom-examples/screen-wake-lock-api/) uses a button to acquire a wake lock and also release it, which in turn updates the UI. The UI also updates if the wake lock is released automatically for any reason. There's a checkbox which when checked, will automatically reacquire the wake lock if the document's visibility state changes and becomes visible again.

### Performance considerations

-   Release the screen wake lock when user ends activity that required always-on screen. For example, a ticketing app which uses QR codes to transmit ticket information, might acquire screen wake lock when the QR code is displayed (so that code is successfully scanned) but release afterwards. A presentation app might hold the lock only while a presentation is active, but not when presentation is being edited.
-   If your app is performing long-running downloads, consider using background fetch.
-   If you app is synchronizing data from a remote server, consider using background sync.
-   Only active documents can acquire screen wake locks and previously acquired locks are automatically released when document becomes inactive. Therefore make sure to re-acquire screen wake lock if necessary when document becomes active (listen for [visibilitychange](document/visibilitychange_event) event).

Feature Policy integration
--------------------------

Access to Screen Wake Lock API is controlled by [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) directive [`screen-wake-lock`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/screen-wake-lock). Refer to [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) for reference how to use it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/screen-wake-lock/">Screen Wake Lock API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

-   [An introductory article on the Screen Wake Lock API](https://web.dev/wakelock/)
-   [A Screen Wake Lock API demo on glitch](https://wake-lock-demo.glitch.me/)
-   [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) directive [`screen-wake-lock`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/screen-wake-lock)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API</a>
