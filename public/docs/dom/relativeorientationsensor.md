RelativeOrientationSensor
=========================

The `RelativeOrientationSensor` interface of the [Sensor APIs](sensor_apis) describes the device's physical orientation without regard to the Earth's reference coordinate system.

To use this sensor, the user must grant permission to the `'accelerometer'`, and `'gyroscope'` device sensors through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Constructor
-----------

[`RelativeOrientationSensor.RelativeOrientationSensor()`](relativeorientationsensor/relativeorientationsensor)  
Creates a new `RelativeOrientationSensor` object.

Properties
----------

*No specific properties; inherits methods from its ancestors [`OrientationSensor`](orientationsensor) and [`Sensor`](sensor).*

### Event handlers

*No specific event handlers; inherits methods from its ancestor, [`Sensor`](sensor).*

Methods
-------

*No specific methods; inherits methods from its ancestors [`OrientationSensor`](orientationsensor) and [`Sensor`](sensor).*

Examples
--------

### Basic Example

The following example, which is loosely based on [Intel's Orientation Phone demo](https://intel.github.io/generic-sensor-demos/orientation-phone/), instantiates an `RelativeOrientationSensor` with a frequency of 60 times a second.

Note that the Intel demo this is based on uses the `AbsoluteOreintationSensor`. On each reading it uses [`OrientationSensor.quaternion`](orientationsensor/quaternion) to rotate a visual model of a phone.

    const options = { frequency: 60, referenceFrame: 'device' };
    const sensor = new RelativeOrientationSensor(options);

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

Using orientation sensors requires requsting permissions for multiple device sensors. Becuase the [`Permissions`](permissions) uses promises, a good way to request permissions is to use [`Promise.all`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all).

    const sensor = new RelativeOrientationSensor();
    Promise.all([navigator.permissions.query({ name: "accelerometer" }),
                 navigator.permissions.query({ name: "gyroscope" })])
           .then(results => {
             if (results.every(result => result.state === "granted")) {
               sensor.start();
               ...
             } else {
               console.log("No permissions to use RelativeOrientationSensor.");
             }
       });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/orientation-sensor/#relativeorientationsensor-interface">Orientation Sensor<br />
<span class="small">The definition of 'RelativeOrientationSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RelativeOrientationSensor`

67

79

No

No

54

No

67

67

?

48

?

9.0

`RelativeOrientationSensor`

67

79

No

No

54

No

67

67

?

48

?

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RelativeOrientationSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RelativeOrientationSensor</a>
