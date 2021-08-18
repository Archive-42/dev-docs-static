Headers.keys()
==============

The `Headers.keys()` method returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all keys contained in this object. The keys are [`ByteString`](../bytestring) objects.

**Note**: This method is available in [Web Workers](../web_workers_api).

Syntax
------

    headers.keys();

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Example
-------

    // Create a test Headers object
    var myHeaders = new Headers();
    myHeaders.append('Content-Type', 'text/xml');
    myHeaders.append('Vary', 'Accept-Language');

    // Display the keys
    for(var key of myHeaders.keys()) {
       console.log(key);
    }

The result is:

    content-type
    vary

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

`keys`

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

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/keys</a>
