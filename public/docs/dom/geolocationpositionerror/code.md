GeolocationPositionError.code
=============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `GeolocationPositionError.code` read-only property is an `unsigned short` representing the error code.

Syntax
------

    let typeErr = geolocationPositionErrorInstance.code

### Value

An `unsigned short` representing the error code. The following values are possible:

<table><thead><tr class="header"><th>Value</th><th>Associated constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>1</code></td><td><code>PERMISSION_DENIED</code></td><td>The acquisition of the geolocation information failed because the page didn't have the permission to do it.</td></tr><tr class="even"><td><code>2</code></td><td><code>POSITION_UNAVAILABLE</code></td><td>The acquisition of the geolocation failed because one or several internal sources of position returned an internal error.</td></tr><tr class="odd"><td><code>3</code></td><td><code>TIMEOUT</code></td><td>The time allowed to acquire the geolocation, defined by <a href="../positionoptions/timeout"><code>PositionOptions.timeout</code></a> information that was reached before the information was obtained.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocationpositionerror-code">Geolocation API<br />
<span class="small">The definition of 'PositionError.code' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [Using geolocation](../geolocation_api/using_the_geolocation_api)
-   [`GeolocationPositionError`](../geolocationpositionerror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPositionError/code" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationPositionError/code</a>
