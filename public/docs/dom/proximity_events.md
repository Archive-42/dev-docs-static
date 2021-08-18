# Proximity Events

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

The Proximity Events APIs are not supported by any current major browser, and should not be used. This page is provided for historical interest.

The **proximity events** are a handy way to know when a user is close to a device. These events make it possible to react to such a change, for example by shutting down the screen of a smartphone when the user is having a phone call with the device close to their ear.

There are two proximity events (see links for documentation.):

- [`UserProximityEvent`](userproximityevent), handled by `window.onuserproximity`
- [`DeviceProximityEvent`](deviceproximityevent), handled by `window.ondeviceproximity`

The difference between them is that [`UserProximityEvent`](userproximityevent) simply notifies `true` when the user is considered "close", while [`DeviceProximityEvent`](deviceproximityevent) provides an estimate of the actual distance to a nearby object.

**Note**

Obviously, the API requires the device to have a proximity sensor, which are mostly available only on mobile devices. Devices without such a sensor may support those events but will never fire them.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/proximity/">Proximity Sensor<br />
<span class="small">The definition of 'Proximity Events' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Proximity_Events" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Proximity_Events</a>
