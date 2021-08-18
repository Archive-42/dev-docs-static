# Headers.values()

The `Headers.values()` method returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all values contained in this object. The values are [`ByteString`](../bytestring) objects.

**Note**: This method is available in [Web Workers](../web_workers_api).

## Syntax

    headers.values();

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

## Example

    // Create a test Headers object
    var myHeaders = new Headers();
    myHeaders.append('Content-Type', 'text/xml');
    myHeaders.append('Vary', 'Accept-Language');

    // Display the values
    for (var value of myHeaders.values()) {
       console.log(value);
    }

The result is:

    text/xml
    Accept-Language

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

`values`

45

16

44

No

32

10.1

45

45

44

32

10.3

5.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/values</a>
