# Accelerometer

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Accelerometer` interface of the [Sensor APIs](sensor_apis) provides on each reading the acceleration applied to the device along all three axes.

To use this sensor, the user must grant permission to the `'accelerometer'`, device sensor through the [`Permissions`](permissions) API.

If a feature policy blocks the use of a feature, it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Constructor

[`Accelerometer.Accelerometer()`](accelerometer/accelerometer)  
Creates a new `Accelerometer` object.

## Properties

[`Accelerometer.x`](accelerometer/x) <span class="badge inline readonly">Read only </span>  
Returns a double containing the acceleration of the device along the device's x axis.

[`Accelerometer.y`](accelerometer/y) <span class="badge inline readonly">Read only </span>  
Returns a double containing the acceleration of the device along the device's y axis.

[`Accelerometer.z`](accelerometer/z) <span class="badge inline readonly">Read only </span>  
Returns a double containing the acceleration of the device along the device's z axis.

## Example

Acceleration is typically read in the [`Sensor.onreading`](sensor/onreading) event callback. In the example below this occurs sixty times a second.

    let acl = new Accelerometer({frequency: 60});

    acl.addEventListener('reading', () => {
      console.log("Acceleration along the X-axis " + acl.x);
      console.log("Acceleration along the Y-axis " + acl.y);
      console.log("Acceleration along the Z-axis " + acl.z);
    });

    acl.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/#accelerometer-interface">Accelerometer<br />
<span class="small">The definition of 'Accelerometer' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`Accelerometer`

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

`Accelerometer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer</a>
