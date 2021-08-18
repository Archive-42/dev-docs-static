Geolocation API
===============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The **Geolocation API** allows the user to provide their location to web applications if they so desire. For privacy reasons, the user is asked for permission to report location information.

WebExtensions that wish to use the `Geolocation` object must add the `"geolocation"` permission to their manifest. The user's operating system will prompt the user to allow location access the first time it is requested.

Concepts and usage
------------------

You will often want to retrieve a user's location information in your web app, for example to plot their location on a map, or display personalized information relevant to their location.

The Geolocation API is accessed via a call to [`navigator.geolocation`](navigator/geolocation); this will cause the user's browser to ask them for permission to access their location data. If they accept, then the browser will use the best available functionality on the device to access this information (for example, GPS).

The developer can now access this location information in a couple of different ways:

-   [`Geolocation.getCurrentPosition()`](geolocation/getcurrentposition): Retrieves the device's current location.
-   [`Geolocation.watchPosition()`](geolocation/watchposition): Registers a handler function that will be called automatically each time the position of the device changes, returning the updated location.

In both cases, the method call takes up to three arguments:

-   A mandatory success callback: If the location retrieval is successful, the callback executes with a [`GeolocationPosition`](geolocationposition) object as its only parameter, providing access to the location data.
-   An optional error callback: If the location retrieval is unsuccessful, the callback executes with a [`GeolocationPositionError`](geolocationpositionerror) object as its only parameter, providing access information on what went wrong.
-   An optional [`PositionOptions`](positionoptions) object, which provides options for retrieval of the position data.

For further information on Geolocation usage, read [Using the Geolocation API](geolocation_api/using_the_geolocation_api).

Interfaces
----------

[`Geolocation`](geolocation)  
The main class of this API — contains methods to retrieve the user's current position, watch for changes in their position, and clear a previously-set watch.

[`GeolocationPosition`](geolocationposition)  
Represents the position of a user. A `GeolocationPosition` instance is returned by a successful call to one of the methods contained inside [`Geolocation`](geolocation), inside a success callback, and contains a timestamp plus a [`GeolocationCoordinates`](geolocationcoordinates) object instance.

[`GeolocationCoordinates`](geolocationcoordinates)  
Represents the coordinates of a user's position; a `GeolocationCoordinates` instance contains latitude, longitude, and other important related information.

[`GeolocationPositionError`](geolocationpositionerror)  
A `GeolocationPositionError` is returned by an unsuccessful call to one of the methods contained inside [`Geolocation`](geolocation), inside an error callback, and contains an error code and message.

[`Navigator.geolocation`](navigator/geolocation)  
The entry point into the API. Returns a [`Geolocation`](geolocation) object instance, from which all other functionality can be accessed.

Dictionaries
------------

[`PositionOptions`](positionoptions)  
Represents an object containing options to pass in as a parameter of [`Geolocation.getCurrentPosition()`](geolocation/getcurrentposition) and [`Geolocation.watchPosition()`](geolocation/watchposition).

Examples
--------

In the following example the Geolocation API is used to retrieve the user's latitude and longitude. If sucessful, the available hyperlink is populated with an `openstreetmap.org` URL that will show their location.

### HTML

    <button id = "find-me">Show my location</button><br/>
    <p id = "status"></p>
    <a id = "map-link" target="_blank"></a>

### JavaScript

    function geoFindMe() {

      const status = document.querySelector('#status');
      const mapLink = document.querySelector('#map-link');

      mapLink.href = '';
      mapLink.textContent = '';

      function success(position) {
        const latitude  = position.coords.latitude;
        const longitude = position.coords.longitude;

        status.textContent = '';
        mapLink.href = `https://www.openstreetmap.org/#map=18/${latitude}/${longitude}`;
        mapLink.textContent = `Latitude: ${latitude} °, Longitude: ${longitude} °`;
      }

      function error() {
        status.textContent = 'Unable to retrieve your location';
      }

      if(!navigator.geolocation) {
        status.textContent = 'Geolocation is not supported by your browser';
      } else {
        status.textContent = 'Locating…';
        navigator.geolocation.getCurrentPosition(success, error);
      }

    }

    document.querySelector('#find-me').addEventListener('click', geoFindMe);

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/">Geolocation API</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`Geolocation_API`

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

### Availability

As WiFi-based locationing is often provided by Google, the vanilla Geolocation API may be unavailable in China. You may use local third-party providers such as [Baidu](https://lbsyun.baidu.com/index.php?title=jspopular/guide/geolocation), [Autonavi](https://lbs.amap.com/api/javascript-api/guide/services/geolocation#geolocation), or [Tencent](https://lbs.qq.com/tool/component-geolocation.html). These services use the user's IP address and/or a local app to provide enhanced positioning.

See also
--------

-   [Using the Geolocation API](geolocation_api/using_the_geolocation_api)
-   [Geolocation API on w3.org](https://www.w3.org/TR/geolocation-API/)
-   [Who moved my geolocation?](https://hacks.mozilla.org/2013/10/who-moved-my-geolocation/) (Hacks blog)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API</a>
