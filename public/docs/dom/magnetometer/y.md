# Magnetometer.y

The `y` read-only property of the [`Magnetometer`](../magnetometer) interface returns a double precision integer containing the magnetic field around the device's y axis.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Syntax

    var magnetometery = magnetometer.x

### Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).

## Example

The magnetometer is typically read in the [`Sensor.onreading`](../sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let magSensor = new Magnetometer({frequency: 60});

    magSensor.addEventListener('reading', e => {
      console.log("Magnetic field along the X-axis " + magSensor.x);
      console.log("Magnetic field along the Y-axis " + magSensor.y);
      console.log("Magnetic field along the Z-axis " + magSensor.z);
    });
    magSensor.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/magnetometer/#magnetometer-y">Magnetometer<br />
<span class="small">The definition of 'y' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`y`

56

79

No

No

43

No

No

56

No

43

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer/y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer/y</a>
