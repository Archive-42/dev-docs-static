# DeviceLightEvent

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

`DeviceLightEvent` is not supported by any current major browser, and should not be used.

The `DeviceLightEvent` provides web developers with information from photo sensors or similar detectors about ambient light levels near the device. For example this may be useful to adjust the screen's brightness based on the current ambient light level in order to save energy or provide better readability.

## Properties

`DeviceLightEvent.value`  
The level of the ambient light in [lux](https://en.wikipedia.org/wiki/Lux).

## Example

    window.addEventListener('devicelight', function(event) {
      console.log(event.value);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ambient-light/">Ambient Light Sensor<br />
<span class="small">The definition of 'Ambient Light Events' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DeviceLightEvent`

No

13-79

62

See [bug 1462308](https://bugzil.la/1462308).

22-61

Not supported for MacBook with Touch Bar and Windows 7 (see [bug 754199](https://bugzil.la/754199)).

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

13-79

62

See [bug 1462308](https://bugzil.la/1462308).

22-61

Not supported for MacBook with Touch Bar and Windows 7 (see [bug 754199](https://bugzil.la/754199)).

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

- [Using Light Events](ambient_light_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceLightEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceLightEvent</a>
