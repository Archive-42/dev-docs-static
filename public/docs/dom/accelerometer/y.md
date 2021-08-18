# Accelerometer.y

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `y` read-only property of the [`Accelerometer`](../accelerometer) interface returns a double precision integer containing the acceleration of the device along the its y axis.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Syntax

    var yAcceleration = accelerometer.y

### Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).

## Example

Acceleration is typically read in the [`Sensor.onreading`](../sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let accelerometer = new Accelerometer({frequency: 60});

    accelerometer.addEventListener('reading', e => {
      console.log("Acceleration along the X-axis " + accelerometer.x);
      console.log("Acceleration along the Y-axis " + accelerometer.y);
      console.log("Acceleration along the Z-axis " + accelerometer.z);
    });
    accelerometer.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/#accelerometer-y">Accelerometer<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer/y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer/y</a>
