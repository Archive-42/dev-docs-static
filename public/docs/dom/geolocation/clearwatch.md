Geolocation.clearWatch()
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Geolocation.clearWatch()` method is used to unregister location/error monitoring handlers previously installed using [`Geolocation.watchPosition()`](watchposition).

Syntax
------

    navigator.geolocation.clearWatch(id);

### Parameters

`id`  
The ID number returned by the [`Geolocation.watchPosition()`](watchposition) method when installing the handler you wish to remove.

Example
-------

    var id, target, option;

    function success(pos) {
      var crd = pos.coords;

      if (target.latitude === crd.latitude && target.longitude === crd.longitude) {
        console.log('Congratulation, you reach the target');
        navigator.geolocation.clearWatch(id);
      }
    };

    function error(err) {
      console.warn('ERROR(' + err.code + '): ' + err.message);
    };

    target = {
      latitude : 0,
      longitude: 0,
    }

    options = {
      enableHighAccuracy: false,
      timeout: 5000,
      maximumAge: 0
    };

    id = navigator.geolocation.watchPosition(success, error, options);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/">Geolocation API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

See also
--------

-   [Using geolocation](../geolocation_api/using_the_geolocation_api)
-   [`Geolocation`](../geolocation)
-   [`Geolocation.watchPosition()`](watchposition)
-   [`Geolocation.getCurrentPosition()`](getcurrentposition)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/clearWatch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/clearWatch</a>
