PositionOptions.maximumAge
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PositionOptions.maximumAge` property is a positive `long` value indicating the maximum age in milliseconds of a possible cached position that is acceptable to return. If set to `0`, it means that the device cannot use a cached position and must attempt to retrieve the real current position. If set to `Infinity` the device must return a cached position regardless of its age.

Syntax
------

    positionOptions.maximumAge = timeLength

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-positionoptions-maximumage">Geolocation API<br />
<span class="small">The definition of 'PositionOptions.maximumAge' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`maximumAge`

5

12

3.5

9

16

10-15

5

≤37

18

4

16

10.1-14

Yes

1.0

See also
--------

-   [Using geolocation](../geolocation_api)
-   The [`PositionOptions`](../positionoptions) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/maximumAge" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/maximumAge</a>
