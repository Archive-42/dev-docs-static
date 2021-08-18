OrientationSensor.quaternion
============================

The `quaternion` read-only property of the [`OrientationSensor`](../orientationsensor) interface returns a four element [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements contain the components of the unit [quaternion](https://developer.mozilla.org/en-US/docs/Glossary/Quaternion) representing the device's orientation.

Syntax
------

    var quaternion = orientationInstance.quaternion

Because [`OrientationSensor`](../orientationsensor) is a base class, `quaternion` may only be read from one of its derived classes.

### Value

A [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose values are the x, y, z, and w components of the quaternion representing the device orientation.

Example
-------

    // TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/orientation-sensor/#orientationsensor-quaternion">Orientation Sensor<br />
<span class="small">The definition of 'quaternion' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`quaternion`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OrientationSensor/quaternion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OrientationSensor/quaternion</a>
