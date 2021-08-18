# LinearAccelerationSensor

The `LinearAccelerationSensor` interface of the [Sensor APIs](sensor_apis) provides on each reading the acceleration applied to the device along all three axes, but without the contribution of gravity.

To use this sensor, the user must grant permission to the `'accelerometer'` device sensor through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Constructor

[`LinearAccelerationSensor.LinearAccelerationSensor()`](linearaccelerationsensor/linearaccelerationsensor)  
Creates a new `LinearAccelerationSensor` object.

## Properties

_Inherits properties from its ancestor, [`Accelerometer`](accelerometer)._

## Example

Linear acceleration is typically read in the [`Sensor.onreading`](sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let laSensor = new LinearAccelerationSensor({frequency: 60});

    laSensor.addEventListener('reading', e => {
      console.log("Linear acceleration along the X-axis " + laSensor.x);
      console.log("Linear acceleration along the Y-axis " + laSensor.y);
      console.log("Linear acceleration along the Z-axis " + laSensor.z);
    });
    laSensor.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/#linearaccelerationsensor-interface">Accelerometer<br />
<span class="small">The definition of 'LinearAccelerationSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`LinearAccelerationSensor`

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

`LinearAccelerationSensor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LinearAccelerationSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LinearAccelerationSensor</a>
