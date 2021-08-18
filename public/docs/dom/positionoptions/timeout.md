PositionOptions.timeout
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PositionOptions.timeout` property is a positive `long` value representing the maximum length of time (in milliseconds) the device is allowed to take in order to return a position. The default value is `Infinity`, meaning that `getCurrentPosition()` won't return until the position is available.

Syntax
------

    positionOptions.timeout = timeLength

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-positionoptions-timeout">Geolocation API<br />
<span class="small">The definition of 'PositionOptions.timeout' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`timeout`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/timeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/timeout</a>
