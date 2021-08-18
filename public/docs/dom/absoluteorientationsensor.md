# AbsoluteOrientationSensor

The `AbsoluteOrientationSensor` interface of the [Sensor APIs](sensor_apis) describes the device's physical orientation in relation to the Earth's reference coordinate system.

To use this sensor, the user must grant permission to the `'accelerometer'`, `'gyroscope'`, and `'magnetometer'` device sensors through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Constructor

[`AbsoluteOrientationSensor.AbsoluteOrientationSensor()`](absoluteorientationsensor/absoluteorientationsensor)  
Creates a new `AbsoluteOrientationSensor` object.

## Properties

_No specific properties; inherits methods from its ancestors [`OrientationSensor`](orientationsensor) and [`Sensor`](sensor)._

### Event handlers

_No specific event handlers; inherits methods from its ancestor, [`Sensor`](sensor)._

## Methods

_No specific methods; inherits methods from its ancestors [`OrientationSensor`](orientationsensor) and [`Sensor`](sensor)._

## Examples

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

Using orientation sensors requires requesting permissions for multiple device sensors. Because the [`Permissions`](permissions) uses promises, a good way to request permissions is to use [`Promise.all`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all).

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/orientation-sensor/#absoluteorientationsensor-interface">Orientation Sensor<br />
<span class="small">The definition of 'AbsoluteOrientationSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`AbsoluteOrientationSensor`

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

`AbsoluteOrientationSensor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbsoluteOrientationSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbsoluteOrientationSensor</a>
