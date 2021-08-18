Magnetometer
============

The `Magnetometer` interface of the [Sensor APIs](sensor_apis) provides information about the magnetic field as detected by the device’s primary magnetometer sensor.

To use this sensor, the user must grant permission to the `'magnetometer'` device sensor through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature, it's because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Constructor
-----------

[`Magnetometer.Magnetometer()`](magnetometer/magnetometer)  
Creates a new `Magnetometer` object.

Properties
----------

 [`Magnetometer.x`](magnetometer/x) <span class="badge inline readonly">Read only </span>   
Returns a double containing the magnetic field around the device's x axis.

 [`Magnetometer.y`](magnetometer/y) <span class="badge inline readonly">Read only </span>   
Returns a double containing the magnetic field around the device's y axis.

 [`Magnetometer.z`](magnetometer/z) <span class="badge inline readonly">Read only </span>   
Returns a double containing the magnetic field around the device's z axis.

Example
-------

The magnetometer is typically read in the [`Sensor.onreading`](sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let magSensor = new Magnetometer({frequency: 60});

    magSensor.addEventListener('reading', e => {
      console.log("Magnetic field along the X-axis " + magSensor.x);
      console.log("Magnetic field along the Y-axis " + magSensor.y);
      console.log("Magnetic field along the Z-axis " + magSensor.z);
    });
    magSensor.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/magnetometer/#magnetometer-interface">Magnetometer<br />
<span class="small">The definition of 'Magnetometer' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`Magnetometer`

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

`Magnetometer`

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

`x`

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

`z`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer</a>
