# GravitySensor

The `GravitySensor` interface of the [Sensor APIs](sensor_apis) provides on each reading the gravity applied to the device along all three axes.

To use this sensor, the user must grant permission to the `'accelerometer'` device sensor through the [`Permissions`](permissions) API.

## Constructor

[`GravitySensor.GravitySensor()`](gravitysensor/gravitysensor)  
Creates a new `GravitySensor` object.

## Properties

_Inherits properties from its ancestor, [`Accelerometer`](accelerometer)._

## Example

Gravity is typically read in the [`Sensor.onreading`](sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let gravitySensor = new GravitySensor({frequency: 60});

    gravitySensor.addEventListener("reading", e => {
      console.log(`Gravity along the X-axis ${gravitySensor.x}`);
      console.log(`Gravity along the Y-axis ${gravitySensor.y}`);
      console.log(`Gravity along the Z-axis ${gravitySensor.z}`);
    });

    gravitySensor.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/#gravitysensor-interface">Accelerometer<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GravitySensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GravitySensor</a>
