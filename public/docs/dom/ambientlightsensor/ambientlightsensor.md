# AmbientLightSensor.AmbientLightSensor()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AmbientLightSensor()` constructor creates a new [`AmbientLightSensor`](../ambientlightsensor) object, which returns the current light level or illuminance of the ambient light around the hosting device.

If a feature policy blocks use of a feature it is because your code is inconsistent with the policies set on your server. This is not something that would ever be shown to a user. See [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) for implementation instructions.

## Syntax

    var ambientLightSensor = new AmbientLightSensor(options)

### Parameters

_options_ <span class="badge inline optional">Optional</span>  
Currently only one option is supported:

- `frequency`: The desired number of times per second a sample should be taken, meaning the number of times per second that [`sensor.onreading`](../sensor/onreading) will be called. A whole number or decimal may be used, the latter for frequencies less than a second. The actual reading frequency depends device hardware and consequently may be less than requested.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/generic-sensor/">Generic Sensor API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines sensors in general.</td></tr><tr class="even"><td><a href="https://w3c.github.io/ambient-light/#dom-ambientlightsensor-ambientlightsensor">Ambient Light Sensor<br />
<span class="small">The definition of 'AmbientLightSensor()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor/AmbientLightSensor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor/AmbientLightSensor</a>
