# GravitySensor.GravitySensor()

The `GravitySensor` constructor creates a new [`GravitySensor`](../gravitysensor) object which provides on each reading the gravity applied to the device along all three axes.

## Syntax

    let gravitySensor = new GravitySensor([options])

### Parameters

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `frequency`: The desired number of times per second a sample should be taken, meaning the number of times per second that [`sensor.onreading`](../sensor/onreading) will be called. A whole number or decimal may be used, the latter for frequencies less than a second. The actual reading frequency depends on device hardware and consequently may be less than requested. The default frequency is the one defined by the underlying platform.
- `referenceFrame`: The local coordinate system representing the reference frame. It can be either `'device'` or `'screen'`. The default is `'device'`.

### Exceptions

SecurityError  
Use of this feature was blocked by a feature policy. If a feature policy blocks use of a feature, it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/#dom-gravitysensor-gravitysensor">Accelerometer<br />
<span class="small">The definition of 'GravitySensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`GravitySensor`

91

91

No

No

Yes

No

91

91

No

Yes

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GravitySensor/GravitySensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GravitySensor/GravitySensor</a>
