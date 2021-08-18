Gyroscope
=========

The `Gyroscope` interface of the [Sensor APIs](sensor_apis) provides on each reading the angular velocity of the device along all three axes.

To use this sensor, the user must grant permission to the `'gyroscope'` device sensor through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Constructor
-----------

[`Gyroscope.Gyroscope()`](gyroscope/gyroscope)  
Creates a new `Gyroscope` object.

Properties
----------

 [`Gyroscope.x`](gyroscope/x) <span class="badge inline readonly">Read only </span>   
Returns a double, containing the angular velocity of the device along the device's x axis.

 [`Gyroscope.y`](gyroscope/y) <span class="badge inline readonly">Read only </span>   
Returns a double, containing the angular velocity of the device along the device's y axis.

 [`Gyroscope.z`](gyroscope/z) <span class="badge inline readonly">Read only </span>   
Returns a double, containing the angular velocity of the device along the device's z axis.

Example
-------

The gyroscope is typically read in the [`Sensor.onreading`](sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let gyroscope = new Gyroscope({frequency: 60});

    gyroscope.addEventListener('reading', e => {
      console.log("Angular velocity along the X-axis " + gyroscope.x);
      console.log("Angular velocity along the Y-axis " + gyroscope.y);
      console.log("Angular velocity along the Z-axis " + gyroscope.z);
    });
    gyroscope.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/gyroscope/#gyroscope-interface">Gyroscope<br />
<span class="small">The definition of 'Gyroscope' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Gyroscope`

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

`Gyroscope`

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

`x`

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

`y`

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

`z`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope</a>
