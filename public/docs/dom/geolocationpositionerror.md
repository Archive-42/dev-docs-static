GeolocationPositionError
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationPositionError` interface represents the reason of an error occurring when using the geolocating device.

Properties
----------

*The `GeolocationPositionError` interface doesn't inherit any property.*

 [`GeolocationPositionError.code`](geolocationpositionerror/code) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns an `unsigned short` representing the error code. The following values are possible:

<table><thead><tr class="header"><th>Value</th><th>Associated constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>1</code></td><td><code>PERMISSION_DENIED</code></td><td>The acquisition of the geolocation information failed because the page didn't have the permission to do it.</td></tr><tr class="even"><td><code>2</code></td><td><code>POSITION_UNAVAILABLE</code></td><td>The acquisition of the geolocation failed because at least one internal source of position returned an internal error.</td></tr><tr class="odd"><td><code>3</code></td><td><code>TIMEOUT</code></td><td>The time allowed to acquire the geolocation, defined by <a href="positionoptions/timeout"><code>PositionOptions.timeout</code></a> information was reached before the information was obtained.</td></tr></tbody></table>

 [`GeolocationPositionError.message`](geolocationpositionerror/message) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a human-readable [`DOMString`](domstring) describing the details of the error. Specifications note that this is primarily intended for debugging use and not to be shown directly in a user interface.

Methods
-------

*The `GeolocationPositionError` interface neither implements nor inherits any method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#position_error_interface">Geolocation API<br />
<span class="small">The definition of 'GeolocationPositionError' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`GeolocationPositionError`

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

`code`

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

`message`

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

See also
--------

-   [Using the Geolocation API](geolocation_api/using_the_geolocation_api)
-   [`Geolocation`](geolocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPositionError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPositionError</a>
