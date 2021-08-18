GeolocationCoordinates.altitude
===============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationCoordinates.altitude` read-only property is a `double` representing the altitude of the position in meters above the [WGS84](https://earth-info.nga.mil/GandG/publications/tr8350.2/wgs84fin.pdf) ellipsoid (which defines the nominal sea level surface). This value is `null` if the implementation cannot provide this data.

Syntax
------

    let alt = geolocationCoordinatesInstance.altitude

### Value

A `double` representing the altitude of the position in meters above the [WGS84](https://earth-info.nga.mil/GandG/publications/tr8350.2/wgs84fin.pdf) ellipsoid.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocationcoordinates-altitude">Geolocation API<br />
<span class="small">The definition of 'Coordinates.altitude' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
-   The [`GeolocationCoordinates`](../geolocationcoordinates) interface it belongs to.
-   [National Imagery and Mapping Agency Technical Report 8350.2, Third Edition (WGS84)](https://earth-info.nga.mil/GandG/publications/tr8350.2/wgs84fin.pdf)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/altitude" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/altitude</a>
