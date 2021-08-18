# GeolocationPosition

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationPosition` interface represents the position of the concerned device at a given time. The position, represented by a [`GeolocationCoordinates`](geolocationcoordinates) object, comprehends the 2D position of the device, on a spheroid representing the Earth, but also its altitude and its speed.

## Properties

_The `GeolocationPosition` interface doesn't inherit any properties._

[`GeolocationPosition.coords`](geolocationposition/coords) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
Returns a [`GeolocationCoordinates`](geolocationcoordinates) object defining the current location.

[`GeolocationPosition.timestamp`](geolocationposition/timestamp) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
Returns a [`DOMTimeStamp`](domtimestamp) representing the time at which the location was retrieved.

## Methods

_The `GeolocationPosition` interface neither implements, nor inherits any methods._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#position_interface">Geolocation API<br />
<span class="small">The definition of 'GeolocationPosition' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`GeolocationPosition`

79

5-78

79

12-79

72

3.5-71

9

16

5

79

≤37-78

79

18-78

4

16

Yes

12.0

1.0-12.0

`coords`

5

12

3.5

9

16

5

≤37

18

4

16

Yes

1.0

`secure_context_required`

47

≤18

55

No

Yes

Yes

47

47

55

Yes

Yes

5.0

`timestamp`

5

12

3.5

9

16

5

≤37

18

4

16

Yes

1.0

## See also

- [Using the Geolocation API](geolocation_api/using_the_geolocation_api)
- [`Geolocation`](geolocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPosition</a>
