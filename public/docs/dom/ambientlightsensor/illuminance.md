# AmbientLightSensor.illuminance

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `illuminance` property of the [`AmbientLightSensor`](../ambientlightsensor) interface returns the current light level in [lux](https://en.wikipedia.org/wiki/Lux) of the ambient light level around the hosting device.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Syntax

    var level = AmbientLightSensor.illuminance

### Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the current light level in lux.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://w3c.github.io/ambient-light/#ambient-light-sensor-reading-attribute">Ambient Light Sensor<br />
<span class="small">The definition of 'illuminance' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor/illuminance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor/illuminance</a>
