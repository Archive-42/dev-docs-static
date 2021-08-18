# GeolocationCoordinates.longitude

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`GeolocationCoordinates`](../geolocationcoordinates) interface's read-only `longitude` property is a double-precision floating point value which represents the longitude of a geographical position, specified in decimal degrees. Together with a [`DOMTimeStamp`](../domtimestamp) indicating a time of measurement, the `GeolocationCoordinates` object is part of the [`GeolocationPosition`](../geolocationposition) interface, which is the object type returned by Geolocation API functions that obtain and return a geographical position.

## Syntax

    let longitude = geolocationCoordinatesInstance.longitude

### Value

The value in `longitude` is the geographical longitude of the location on Earth described by the `Coordinates` object, in decimal degrees. The value is defined by the World Geodetic System 1984 specification (WGS 84).

**Note**: The zero meridian (also known as the prime meridian or the reference meridian) is not precisely the same as the Greenwhich meridian that most people think of. It is, instead, the [IERS Reference Meridian](#), which is located 5.3 [arcseconds](https://en.wikipedia.org/wiki/Arcseconds) (102 meters / 335 feet) east of the [Greenwich meridian](https://en.wikipedia.org/wiki/Greenwich_meridian). This is the same standard used by the [Global Positioning System](#) (GPS).

## Examples

In this simple example, we fetch the user's location and display the resulting coordinates once they're returned.

### JavaScript

The JavaScript code below creates an event listener so that when the user clicks on a button, the location information is retrieved and displayed.

    let button = document.getElementById("get-location");
    let latText = document.getElementById("latitude");
    let longText = document.getElementById("longitude");

    button.addEventListener("click", function() {
      navigator.geolocation.getCurrentPosition(function(position) {
        let lat = position.coords.latitude;
        let long = position.coords.longitude;

        latText.innerText = lat.toFixed(2);
        longText.innerText = long.toFixed(2);
      });
    });

After setting up variables to more conveniently reference the button element and the two elements into which the latitude and logitude will be drawn, the event listener is established by calling [`addEventListener()`](../eventtarget/addeventlistener) on the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element. When the user clicks the button, we'll fetch and display the location information.

Upon receiving a `click` event, we call [`getCurrentPosition()`](../geolocation/getcurrentposition) to request the device's current position. This is an asynchronous request, so we provide a callback which receives as in put a [`GeolocationPosition`](../geolocationposition) object describing the determined position.

From the `GeolocationPosition` object, we obtain the user's latitude and longitude using [`position.coords.latitude`](latitude) and `position.coords.longitude` so we can update the displayed coordinates. The two [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) elements are updated to display the corresponding values after being converted to a value with two decimal places.

### HTML

The HTML used to present the results looks like this:

    <p>
      Your location is <span id="latitude">0.00</span>°
      latitude by <span id="longitude">0.00</span>° longitude.
    </p>
    <button id="get-location">
      Get My Location
    </button>

### Result

Take this example for a test drive here:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocationcoordinates-longitude">Geolocation API<br />
<span class="small">The definition of 'Coordinates.longitude' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
- The [`GeolocationCoordinates`](../geolocationcoordinates) interface it belongs to.
- The [`GeolocationPosition`](../geolocationposition) interface, which is the top-level interface used to return geolocation data from the Geolocation API functions [`Geolocation.getCurrentPosition()`](../geolocation/getcurrentposition) and [`watchPosition()`](../geolocation/watchposition).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/longitude" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GeolocationCoordinates/longitude</a>
