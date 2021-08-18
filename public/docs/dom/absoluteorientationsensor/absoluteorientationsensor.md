# AbsoluteOrientationSensor

The `AbsoluteOrientationSensor` constructor creates a new [`AbsoluteOrientationSensor`](../absoluteorientationsensor) object which describes the device's physical orientation in relation to the Earth's reference coordinate system.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Syntax

    var absoluteOrientationSensor = new AbsoluteOrientationSensor([options])

### Parameters

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `frequency`: The desired number of times per second a sample should be taken, meaning the number of times per second that [`sensor.onreading`](../sensor/onreading) will be called. A whole number or decimal may be used, the latter for frequencies less than a second. The actual reading frequency depends device hardware and consequently may be less than requested.
- `referenceFrame`: Either `'device'` or `'screen'`. The default is `'device'`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/orientation-sensor/#dom-absoluteorientationsensor-absoluteorientationsensor">Orientation Sensor<br />
<span class="small">The definition of 'AbsoluteOrientationSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`AbsoluteOrientationSensor`

67

79

No

No

54

No

67

67

No

48

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbsoluteOrientationSensor/AbsoluteOrientationSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbsoluteOrientationSensor/AbsoluteOrientationSensor</a>
