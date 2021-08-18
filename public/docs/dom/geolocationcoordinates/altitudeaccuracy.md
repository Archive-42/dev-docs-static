GeolocationCoordinates.altitudeAccuracy
=======================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationCoordinates.altitudeAccuracy` read-only property is a strictly positive `double` representing the accuracy, with a 95% confidence level, of the `altitude` expressed in meters. This value is `null` if the implementation doesn't support measuring altitude.

Syntax
------

    let altAcc = geolocationCoordinatesInstance.altitudeAccuracy

### Value

A positive `double` representing the accuracy, with a 95% confidence level, of the `altitude` expressed in meters.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocationcoordinates-altitudeaccuracy">Geolocation API<br />
<span class="small">The definition of 'GeolocationCoordinates.altitudeAccuracy' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

See also
--------

-   [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
-   [`GeolocationCoordinates`](../geolocationcoordinates)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/altitudeAccuracy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/altitudeAccuracy</a>
