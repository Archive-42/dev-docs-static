GeolocationCoordinates.heading
==============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationCoordinates.heading` read-only property is a `double` representing the direction in which the device is traveling. This value, specified in degrees, indicates how far off from heading due north the device is. `Zero` degrees represents true north, and the direction is determined clockwise (which means that east is `90` degrees and west is `270` degrees). If [`GeolocationCoordinates.speed`](speed) is `0`, `heading` is `NaN`. If the device is not able to provide heading information, this value is `null`.

Syntax
------

    let heading = geolocationCoordinatesInstance.heading

### Value

A `double` representing the direction in which the device is traveling.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocationcoordinates-heading">Geolocation API<br />
<span class="small">The definition of 'GeolocationCoordinates.heading' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

See also
--------

-   [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
-   [`GeolocationCoordinates`](../geolocationcoordinates)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/heading" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/heading</a>
