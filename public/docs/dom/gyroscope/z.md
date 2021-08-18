Gyroscope.z
===========

The `z` read-only property of the [`Gyroscope`](../gyroscope) interface returns a double precision integer containing the angular velocity of the device along the its z axis.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Syntax
------

    var z = gyroscope.z

### Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).

Example
-------

The gyroscope is typically read in the [`Sensor.onreading`](../sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let gyroscope = new Gyroscope({frequency: 60});

    gyroscope.addEventListener('reading', e => {
      console.log("Angular velocity along the X-axis " + gyroscope.x);
      console.log("Angular velocity along the Y-axis " + gyroscope.y);
      console.log("Angular velocity along the Z-axis " + gyroscope.z);
    });
    gyroscope.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/gyroscope/#gyroscope-z">Gyroscope<br />
<span class="small">The definition of 'z' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope/z" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope/z</a>
