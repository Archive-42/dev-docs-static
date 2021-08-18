# AmbientLightSensor

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AmbientLightSensor` interface of the [Sensor APIs](sensor_apis) returns the current light level or illuminance of the ambient light around the hosting device.

To use this sensor, the user must grant permission to the `'ambient-light-sensor'` device sensor through the [`Permissions`](permissions) API.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Constructor

[`AmbientLightSensor.AmbientLightSensor()`](ambientlightsensor/ambientlightsensor)  
Creates a new `AmbientLightSensor` object.

## Properties

[`AmbientLightSensor.illuminance`](ambientlightsensor/illuminance)  
Returns the current light level in [lux](https://en.wikipedia.org/wiki/Lux) of the ambient light level around the hosting device.

## Example

    if ( 'AmbientLightSensor' in window ) {
      const sensor = new AmbientLightSensor();
      sensor.onreading = () => {
        console.log('Current light level:', sensor.illuminance);
      };
      sensor.onerror = (event) => {
        console.log(event.error.name, event.error.message);
      };
      sensor.start();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://w3c.github.io/ambient-light/#ambient-light-sensor-interface">Ambient Light Sensor<br />
<span class="small">The definition of 'AmbientLightSensor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`AmbientLightSensor`

56

79

No

No

43

No

No

56

No

43

No

No

`AmbientLightSensor`

56

79

No

No

43

No

No

56

No

43

No

No

`illuminance`

56

In Chrome 79, this method stopped returning floats and returned integers to avoid fingerprinting.

79

No

No

43

In Opera 66, this method stopped returning floats and returned integers to avoid fingerprinting.

No

No

56

In Chrome for Android 79, this method stopped returning floats and returned integers to avoid fingerprinting.

No

43

In Opera for Android 57, this method stopped returning floats and returned integers to avoid fingerprinting.

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor</a>
