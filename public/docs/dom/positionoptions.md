PositionOptions
===============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PositionOptions` dictionary describes an object containing option properties to pass as a parameter of [`Geolocation.getCurrentPosition()`](geolocation/getcurrentposition) and [`Geolocation.watchPosition()`](geolocation/watchposition).

Properties
----------

 [`PositionOptions.enableHighAccuracy`](positionoptions/enablehighaccuracy) <span class="notecard inline secure">Secure context</span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates the application would like to receive the best possible results. If `true` and if the device is able to provide a more accurate position, it will do so. Note that this can result in slower response times or increased power consumption (with a GPS chip on a mobile device for example). On the other hand, if `false`, the device can take the liberty to save resources by responding more quickly and/or using less power. Default: `false`.

 [`PositionOptions.timeout`](positionoptions/timeout) <span class="notecard inline secure">Secure context</span>   
Is a positive `long` value representing the maximum length of time (in milliseconds) the device is allowed to take in order to return a position. The default value is `Infinity`, meaning that `getCurrentPosition()` won't return until the position is available.

 [`PositionOptions.maximumAge`](positionoptions/maximumage) <span class="notecard inline secure">Secure context</span>   
Is a positive `long` value indicating the maximum age in milliseconds of a possible cached position that is acceptable to return. If set to `0`, it means that the device cannot use a cached position and must attempt to retrieve the real current position. If set to `Infinity` the device must return a cached position regardless of its age. Default: 0.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#position_options_interface">Geolocation API<br />
<span class="small">The definition of 'PositionOptions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`PositionOptions`

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

5

1.0

`enableHighAccuracy`

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

`secure_context_required`

50

≤79

55

No

37

Yes

51

Secure context is only required for applications targeting Android Nougat (7) and higher. See [bug 603574](https://crbug.com/603574).

50

55

37

Yes

5.0

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

-   [Using the Geolocation API](geolocation_api/using_the_geolocation_api)
-   The [`Geolocation`](geolocation) interface that uses it.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions</a>
