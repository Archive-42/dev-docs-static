Navigator.geolocation
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Navigator.geolocation` read-only property returns a [`Geolocation`](../geolocation) object that gives Web content access to the location of the device. This allows a Web site or app to offer customized results based on the user's location.

**Note:** For security reasons, when a web page tries to access location information, the user is notified and asked to grant permission. Be aware that each browser has its own policies and methods for requesting this permission.

Syntax
------

    geo = navigator.geolocation

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-navigator-geolocation">Geolocation API<br />
<span class="small">The definition of 'Navigator.geolocation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`geolocation`

5

12

3.5

9

10.6

5

≤37

18

4

11

4.2

1.0

`hid`

89

89

No

No

75

No

No

No

No

No

No

No

`secure_context_required`

47

≤79

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

-   [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/geolocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/geolocation</a>
