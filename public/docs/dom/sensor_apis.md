Sensor APIs
===========

The Sensor APIs are a set of interfaces built to a common design that expose device sensors in a consistent way to the web platform.

Sensor APIs concepts and usage
------------------------------

Although the Generic Sensor API specification defines a [`Sensor`](sensor) interface, as a web developer you will never use it. Instead you'll use one of its subclasses to retrieve specific kinds of sensor data. For example, the [`accelerometer`](accelerometer) interface returns the acceleration of the device along all three axes at the time it is read.

Sensors may or may not correspond exactly to a physical device sensor. For example, the [`Gyroscope`](gyroscope) interface corresponds exactly to a physical device interface. Alternatively, the [`AbsoluteOrientationSensor`](absoluteorientationsensor) interface provides information that is algorithmically agregated from two or more device sensors. These sensor types are referred to as *low-level* and *high-level* respectively. The latter type of sensor is also called a fusion sensor (alternatively, virtual or synthetic sensors).

### Feature detection

Sensor interfaces are only proxies for the underlying device sensors. Consequently, feature detection is more complicated for sensors than it is for other APIs. The presence of a sensor API does not tell you whether that API is connected to a real hardware sensor, whether that sensor works, if it's still connected, or even whether the user has granted access to it. Making all this information consistently available is costly to performance and battery life.

Therefore, feature detection for sensor APIs must include both detection of the APIs themselves and [defensive programming strategies (see below)](#defensive_programming).

The examples below show three methods for detecting sensor APIs. Additionally you can put object instantiation inside a [`try...catch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) block. Notice that detection through the [`Navigator`](navigator) interface is not one of the available options.

    if (typeof Gyroscope === "function") {
        // run in circles...
    }

    if ("ProximitySensor" in window) {
        // watch out!
    }

    if (window.AmbientLightSensor) {
        // go dark...
    }

### Defensive programming

As stated in Feature Detection, checking for a particular sensor API is insufficient for feature detection. The existence of an actual sensor must be confirmed as well. This is where defensive programming is needed. Defensive programming requires three strategies.

-   Checking for thrown errors when instantiating a sensor object.
-   Listening for errors thrown during its use.
-   Handling the errors gracefully so that the user experience is enhanced rather than degraded.

The code example below illustrates these principles. The [`try...catch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) block catches errors thrown during sensor instantiation. It implements a handler for [`Sensor.onerror`](sensor/onerror) to catch errors thrown during use. The only time anything is shown to the user is when [permissions](permissions_api) need to be requested and when the sensor type isn't supported by the device.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

    let accelerometer = null;
    try {
        accelerometer = new Accelerometer({ referenceFrame: 'device' });
        accelerometer.addEventListener('error', event => {
            // Handle runtime errors.
            if (event.error.name === 'NotAllowedError') {
                // Branch to code for requesting permission.
            } else if (event.error.name === 'NotReadableError' ) {
                console.log('Cannot connect to the sensor.');
            }
        });
        accelerometer.addEventListener('reading', () => reloadOnShake(accelerometer));
        accelerometer.start();
    } catch (error) {
        // Handle construction errors.
        if (error.name === 'SecurityError') {
            // See the note above about feature policy.
            console.log('Sensor construction was blocked by a feature policy.');
        } else if (error.name === 'ReferenceError') {
            console.log('Sensor is not supported by the User Agent.');
        } else {
            throw error;
        }
    }

### Permissions and Feature Policy

Sensor readings may not be taken unless the user grants permission to a specific sensor type. Do this using the [`Permissions`](permissions) API. A brief example, shown below, requests permission before attempting to use the sensor.

    navigator.permissions.query({ name: 'accelerometer' })
    .then(result => {
      if (result.state === 'denied') {
        console.log('Permission to use accelerometer sensor is denied.');
        return;
      }
      // Use the sensor.
    });

An alternative approach is to attempt to use the error and listen for the `SecurityError`.

    const sensor = new AbsoluteOrientationSensor();
    sensor.start();
    sensor.onerror = event => {
      if (event.error.name === 'SecurityError')
        console.log("No permissions to use AbsoluteOrientationSensor.");
    };

The following table describes for each sensor type, the name required for the Permissions API, the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element's `allow` attribute and the [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) directive.

<table><caption>Sensor permissions</caption><thead><tr class="header"><th>Sensor</th><th>Permission/Feature Policy Name</th></tr></thead><tbody><tr class="odd"><td><code>AbsoluteOrientationSensor</code></td><td><code>'accelerometer'</code>, <code>'gyroscope'</code>, and <code>'magnetometer'</code></td></tr><tr class="even"><td><code>Accelerometer</code></td><td><code>'accelerometer'</code></td></tr><tr class="odd"><td><code>AmbientLightSensor</code></td><td><code>'ambient-light-sensor'</code></td></tr><tr class="even"><td><code>GravitySensor</code></td><td><code>'accelerometer'</code></td></tr><tr class="odd"><td><code>Gyroscope</code></td><td><code>'gyroscope'</code></td></tr><tr class="even"><td><code>LinearAccelerationSensor</code></td><td><code>'accelerometer'</code></td></tr><tr class="odd"><td><code>Magnetometer</code></td><td><code>'magnetometer'</code></td></tr><tr class="even"><td><code>RelativeOrientationSensor</code></td><td><code>'accelerometer'</code>, and <code>'gyroscope'</code></td></tr></tbody></table>

### Readings

Sensor readings are received through the [`Sensor.onreading`](sensor/onreading) callback which is inherited by all sensor types. Reading frequency is decided by you, accomplished with an option passed to a sensor's constructor. The option is a number that specifies the number of readings per second. A whole number or decimal may be used, the latter for frequencies less than a second. The actual reading frequency depends device hardware and consequently may be less than requested.

The following example illustrates this using the [`Magnetometer`](magnetometer) sensor.

    let magSensor = new Magnetometer({frequency: 60});

    magSensor.addEventListener('reading', e => {
      console.log("Magnetic field along the X-axis " + magSensor.x);
      console.log("Magnetic field along the Y-axis " + magSensor.y);
      console.log("Magnetic field along the Z-axis " + magSensor.z);
    })
    magSensor.addEventListener('error', event => {
      console.log(event.error.name, event.error.message);
    })
    magSensor.start();

Interfaces
----------

 [`AbsoluteOrientationSensor`](absoluteorientationsensor)<span class="notecard inline secure">Secure context</span>   
Describes the device's physical orientation in relation to the Earth's reference coordinate system.

 [`Accelerometer`](accelerometer)<span class="notecard inline secure">Secure context</span>   
Provides the acceleration applied to the device along all three axes.

 [`AmbientLightSensor`](ambientlightsensor)<span class="notecard inline secure">Secure context</span>   
Returns the current light level or illuminance of the ambient light around the hosting device.

 [`GravitySensor`](gravitysensor)<span class="notecard inline secure">Secure context</span>   
Provides the gravity applied to the device along all three axes.

 [`Gyroscope`](gyroscope)<span class="notecard inline secure">Secure context</span>   
Provides the angular velocity of the device along all three axes.

 [`LinearAccelerationSensor`](linearaccelerationsensor)<span class="notecard inline secure">Secure context</span>   
Provides the acceleration applied to the device along all three axes, but without the contribution of gravity.

 [`Magnetometer`](magnetometer)<span class="notecard inline secure">Secure context</span>   
Provides information about the magnetic field as detected by the device’s primary magnetometer sensor.

 [`OrientationSensor`](orientationsensor)<span class="notecard inline secure">Secure context</span>   
The base class for the [`AbsoluteOrientationSensor`](absoluteorientationsensor). This interface cannot be used directly, instead it provides properties and methods accessed by interfaces that inherit from it.

 [`RelativeOrientationSensor`](relativeorientationsensor)<span class="notecard inline secure">Secure context</span>   
Describes the device's physical orientation without regard to the Earth's reference coordinate system.

 [`Sensor`](sensor)<span class="notecard inline secure">Secure context</span>   
The base class for all the other sensor interfaces. This interface cannot be used directly. Instead it provides properties, event handlers, and methods accessed by interfaces that inherit from it.

 [`SensorErrorEvent`](sensorerrorevent)<span class="notecard inline secure">Secure context</span>   
Provides information about errors thrown by a [`Sensor`](sensor) or related interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/accelerometer/">Accelerometer</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>Accelerometer</code>, <code>GravitySensor</code>, and <code>LinearAccelerationSensor</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/ambient-light/">Ambient Light Sensor</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/gyroscope/">Gyroscope</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/magnetometer/">Magnetometer</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/orientation-sensor/">Orientation Sensor</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>AbsoluteOrientationSensor</code> and <code>RelativeOrientationSensor</code>.</td></tr></tbody></table>

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

`Sensor_APIs`

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

`activated`

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

`hasReading`

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

`onactivate`

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

`onerror`

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

`onreading`

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

`start`

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

`stop`

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

`timestamp`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sensor_APIs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sensor_APIs</a>
