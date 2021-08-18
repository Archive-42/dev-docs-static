# Geolocation.getCurrentPosition()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Geolocation.getCurrentPosition()` method is used to get the current position of the device.

## Syntax

    navigator.geolocation.getCurrentPosition(success[, error[, [options]])

### Parameters

`success`  
A callback function that takes a [`GeolocationPosition`](../geolocationposition) object as its sole input parameter.

`error` <span class="badge inline optional">Optional</span>  
An optional callback function that takes a [`GeolocationPositionError`](../geolocationpositionerror) object as its sole input parameter.

`options` <span class="badge inline optional">Optional</span>  
An optional [`PositionOptions`](../positionoptions) object.  
Options includes:

- `maximumAge`: integer (milliseconds) | infinity - maximum cached position age.
- `timeout`: integer (milliseconds) - amount of time before the error callback is invoked, if 0 it will never invoke.
- `enableHighAccuracy`: false | true

## Examples

    var options = {
      enableHighAccuracy: true,
      timeout: 5000,
      maximumAge: 0
    };

    function success(pos) {
      var crd = pos.coords;

      console.log('Your current position is:');
      console.log(`Latitude : ${crd.latitude}`);
      console.log(`Longitude: ${crd.longitude}`);
      console.log(`More or less ${crd.accuracy} meters.`);
    }

    function error(err) {
      console.warn(`ERROR(${err.code}): ${err.message}`);
    }

    navigator.geolocation.getCurrentPosition(success, error, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/">Geolocation API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
- [`Navigator.geolocation`](../navigator/geolocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition</a>
