GeolocationCoordinates
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationCoordinates` interface represents the position and altitude of the device on Earth, as well as the accuracy with which these properties are calculated.

Properties
----------

*The `GeolocationCoordinates` interface doesn't inherit any properties.*

 [`GeolocationCoordinates.latitude`](geolocationcoordinates/latitude) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the position's latitude in decimal degrees.

 [`GeolocationCoordinates.longitude`](geolocationcoordinates/longitude) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the position's longitude in decimal degrees.

 [`GeolocationCoordinates.altitude`](geolocationcoordinates/altitude) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the position's altitude in meters, relative to sea level. This value can be `null` if the implementation cannot provide the data.

 [`GeolocationCoordinates.accuracy`](geolocationcoordinates/accuracy) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the accuracy of the `latitude` and `longitude` properties, expressed in meters.

 [`GeolocationCoordinates.altitudeAccuracy`](geolocationcoordinates/altitudeaccuracy) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the accuracy of the `altitude` expressed in meters. This value can be `null`.

 [`GeolocationCoordinates.heading`](geolocationcoordinates/heading) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the direction towards which the device is facing. This value, specified in degrees, indicates how far off from heading true north the device is. `0` degrees represents true north, and the direction is determined clockwise (which means that east is `90` degrees and west is `270` degrees). If `speed` is `0`, `heading` is `NaN`. If the device is unable to provide `heading` information, this value is `null`.

 [`GeolocationCoordinates.speed`](geolocationcoordinates/speed) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns a `double` representing the velocity of the device in meters per second. This value can be `null`.

Methods
-------

*The `GeolocationCoordinates` interface neither implements, nor inherits any method.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#coordinates_interface">Geolocation API<br />
<span class="small">The definition of 'GeolocationCoordinates' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`GeolocationCoordinates`

79

5-78

79

12-79

72

3.5-71

9

16

10.6-15

5

79

≤37-78

79

18-78

4

16

11-14

4.2

1.0

`accuracy`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`altitude`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`altitudeAccuracy`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`heading`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`latitude`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`longitude`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

`secure_context_required`

47

≤79

55

No

Yes

Yes

No

47

55

Yes

Yes

5.0

`speed`

5

12

3.5

9

16

10.6-15

5

≤37

18

4

16

11-14

?

1.0

See also
--------

-   [Using the Geolocation API](geolocation_api/using_the_geolocation_api)
-   [`Geolocation`](geolocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates</a>
