OrientationSensor
=================

The `OrientationSensor` interface of the [Sensor APIs](sensor_apis) is the base class for orientation sensors. This interface cannot be used directly. Instead it provides properties and methods accessed by interfaces that inherit from it.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Interfaces based on OrientationSensor
-------------------------------------

Below is a list of interfaces based on the OrientationSensor interface.

-   [`AbsoluteOrientationSensor`](absoluteorientationsensor)
-   [`RelativeOrientationSensor`](relativeorientationsensor)

Properties
----------

[`OrientationSensor.quaternion`](orientationsensor/quaternion)  
Returns a four element [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements contain the components of the unit quaternion representing the device's orientation.

Methods
-------

[`OrientationSensor.populateMatrix()`](orientationsensor/populatematrix)  
Populates the given object with the rotation matrix based on the latest sensor reading. The rotation maxtrix is shown below.

Examples
--------

### Basic Example

The following example, which is loosely based on [Intel's Orientation Phone demo](https://intel.github.io/generic-sensor-demos/orientation-phone/), instantiates an `AbsoluteOrientationSensor` with a frequency of 60 times a second. On each reading it uses [`OrientationSensor.quaternion`](orientationsensor/quaternion) to rotate a visual model of a phone.

    const options = { frequency: 60, referenceFrame: 'device' };
    const sensor = new AbsoluteOrientationSensor(options);

    sensor.addEventListener('reading', () => {
      // model is a Three.js object instantiated elsewhere.
      model.quaternion.fromArray(sensor.quaternion).inverse();
    });
    sensor.addEventListener('error', error => {
      if (event.error.name == 'NotReadableError') {
        console.log("Sensor is not available.");
      }
    });
    sensor.start();

### Permissions Example

Using orientation sensors requires requsting permissions for multiple device sensors. Because the [`Permissions`](permissions) uses promises, a good way to request permissions is to use [`Promise.all`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all).

    const sensor = new AbsoluteOrientationSensor();
    Promise.all([navigator.permissions.query({ name: "accelerometer" }),
                 navigator.permissions.query({ name: "magnetometer" }),
                 navigator.permissions.query({ name: "gyroscope" })])
           .then(results => {
             if (results.every(result => result.state === "granted")) {
               sensor.start();
               ...
             } else {
               console.log("No permissions to use AbsoluteOrientationSensor.");
             }
       });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/orientation-sensor/#orientationsensor-interface">Orientation Sensor<br />
<span class="small">The definition of 'OrientationSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OrientationSensor`

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

`populateMatrix`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OrientationSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OrientationSensor</a>
