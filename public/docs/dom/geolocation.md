# Geolocation

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Geolocation` interface represents an object able to programmatically obtain the position of the device. It gives Web content access to the location of the device. This allows a Web site or app to offer customized results based on the user's location.

An object with this interface is obtained using the [`navigator.geolocation`](navigator/geolocation) property implemented by the [`Navigator`](navigator) object.

**Note:** For security reasons, when a web page tries to access location information, the user is notified and asked to grant permission. Be aware that each browser has its own policies and methods for requesting this permission.

## Properties

_The `Geolocation` interface neither implements, nor inherits any property._

## Methods

_The `Geolocation` interface doesn't inherit any method._

[`Geolocation.getCurrentPosition()`](geolocation/getcurrentposition) <span class="notecard inline secure">Secure context</span>  
Determines the device's current location and gives back a [`GeolocationPosition`](geolocationposition) object with the data.

[`Geolocation.watchPosition()`](geolocation/watchposition) <span class="notecard inline secure">Secure context</span>  
Returns a `long` value representing the newly established callback function to be invoked whenever the device location changes.

[`Geolocation.clearWatch()`](geolocation/clearwatch) <span class="notecard inline secure">Secure context</span>  
Removes the particular handler previously installed using `watchPosition()`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#geolocation_interface">Geolocation API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`Geolocation`

5

12

3.5

[GPSD](http://catb.org/gpsd/) (GPS daemon) support added in Firefox 3.6. WiFi-based location is provided by Google ([privacy](https://support.mozilla.org/en-US/kb/does-firefox-share-my-location-websites)) or a custom provider ([MLS instructions](https://wiki.mozilla.org/CloudServices/Location/Software)).

9

10.6

5

≤37

18

4

11

5

1.0

`clearWatch`

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

5

1.0

`getCurrentPosition`

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

5

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

`watchPosition`

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

5

1.0

## See also

- [Using geolocation](geolocation_api/using_the_geolocation_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Geolocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Geolocation</a>
