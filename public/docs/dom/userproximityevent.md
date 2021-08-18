UserProximityEvent
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

`UserProximityEvent` is not supported by any current major browser, and should not be used.

The `UserProximityEvent` indicates whether a nearby physical object is present by using the proximity sensor of a device.

Properties
----------

`UserProximityEvent.near`  
Indicates if the device has sensed a nearby physical object.

Examples
--------

    window.addEventListener('userproximity', function(event) {
      if (event.near) {
        // let's power off the screen
        navigator.mozPower.screenEnabled = false;
      } else {
        // Otherwise, let's power on the screen
        navigator.mozPower.screenEnabled = true;
      }
    });

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

`UserProximityEvent`

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

Yes-61

No

No

No

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

Yes-61

No

No

No

`near`

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

Yes-61

No

No

No

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

15-61

No

No

No

See also
--------

-   [Proximity Events](proximity_events)
-   [`DeviceProximityEvent`](deviceproximityevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UserProximityEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UserProximityEvent</a>
