# Geolocation.watchPosition()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`Geolocation`](../geolocation) method `watchPosition()` method is used to register a handler function that will be called automatically each time the position of the device changes. You can also, optionally, specify an error handling callback function.

## Syntax

    navigator.geolocation.watchPosition(success[, error[, options]])

### Parameters

`success`  
A callback function that takes a [`GeolocationPosition`](../geolocationposition) object as an input parameter.

`error` <span class="badge inline optional">Optional</span>  
An optional callback function that takes a [`GeolocationPositionError`](../geolocationpositionerror) object as an input parameter.

`options` <span class="badge inline optional">Optional</span>  
An optional [`PositionOptions`](../positionoptions) object that provides configuration options for the location watch.

### Return value

An integer ID that identifies the registered handler. The ID can be passed to the [`Geolocation.clearWatch()`](clearwatch) to unregister the handler.

## Examples

    var id, target, options;

    function success(pos) {
      var crd = pos.coords;

      if (target.latitude === crd.latitude && target.longitude === crd.longitude) {
        console.log('Congratulations, you reached the target');
        navigator.geolocation.clearWatch(id);
      }
    }

    function error(err) {
      console.warn('ERROR(' + err.code + '): ' + err.message);
    }

    target = {
      latitude : 0,
      longitude: 0
    };

    options = {
      enableHighAccuracy: false,
      timeout: 5000,
      maximumAge: 0
    };

    id = navigator.geolocation.watchPosition(success, error, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-geolocation-watchposition">Geolocation API<br />
<span class="small">The definition of 'watchPosition()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

- [Using the Geolocation API](../geolocation_api/using_the_geolocation_api)
- The interface it belongs to, [`Geolocation`](../geolocation), and the way to access it — [`Navigator.geolocation`](../navigator/geolocation).
- The opposite operation: [`Geolocation.clearWatch()`](clearwatch)
- A similar method: [`Geolocation.getCurrentPosition()`](getcurrentposition)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition</a>
