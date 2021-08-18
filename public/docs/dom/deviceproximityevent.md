# DeviceProximityEvent

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

`DeviceProximityEvent` is not supported by any current major browser, and should not be used.

The `DeviceProximityEvent` interface provides information about the distance of a nearby physical object using the proximity sensor of a device.

## Properties

`DeviceProximityEvent.max` <span class="badge inline readonly">Read only </span>  
The maximum sensing distance the sensor is able to report, in centimeters.

`DeviceProximityEvent.min` <span class="badge inline readonly">Read only </span>  
The minimum sensing distance the sensor is able to report, in centimeters. Ususally zero.

`DeviceProximityEvent.value` <span class="badge inline readonly">Read only </span>  
The current device proximity, in centimeters.

## Examples

    window.addEventListener('deviceproximity', function(event) {
      console.log("value: " + event.value, "max: " + event.max, "min: " + event.min);
    });

## Browser compatibility

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

`DeviceProximityEvent`

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

`max`

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

`min`

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

`value`

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

## See also

- [`UserProximityEvent`](userproximityevent)
- [Proximity API](proximity_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceProximityEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceProximityEvent</a>
