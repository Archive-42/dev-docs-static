Sensor
======

The `Sensor` interface of the [Sensor APIs](sensor_apis) is the base class for all the other sensor interfaces. This interface cannot be used directly. Instead it provides properties, event handlers, and methods accessed by interfaces that inherit from it.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

Interfaces based on Sensor
--------------------------

Below is a list of interfaces based on the Sensor interface.

-   [`Accelerometer`](accelerometer)
-   [`AmbientLightSensor`](ambientlightsensor)
-   [`GravitySensor`](gravitysensor)
-   [`Gyroscope`](gyroscope)
-   [`LinearAccelerationSensor`](linearaccelerationsensor)
-   [`Magnetometer`](magnetometer)
-   [`OrientationSensor`](orientationsensor)

Properties
----------

 [`Sensor.activated`](sensor/activated) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the sensor is active.

 [`Sensor.hasReading`](sensor/hasreading) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the sensor has a reading.

 [`Sensor.timestamp`](sensor/timestamp) <span class="badge inline readonly">Read only </span>   
Returns the time stamp of the latest sensor reading.

### Event handlers

[`Sensor.onerror`](sensor/onerror)  
Called when an error occurs on one of the child interfaces of the `Sensor` interface.

[`Sensor.onreading`](sensor/onreading)  
Called when a reading is taken on one of the child interfaces of the Sensor interface.

[`Sensor.onactivate`](sensor/onactivate)  
Called when one of the Sensor interface's becomes active.

Methods
-------

[`Sensor.start()`](sensor/start)  
Activates one of the sensors based on `Sensor`.

[`Sensor.stop()`](sensor/stop)  
Deactivates one of the sensors based on `Sensor`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/#the-sensor-interface">Generic Sensor API<br />
<span class="small">The definition of 'Sensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Sensor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sensor</a>
