Headers.getAll()
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getAll()` method of the [`Headers`](../headers) interface used to return an array of all the values of a header within a `Headers` object with a given name; in newer versions of the Fetch spec, it has been deleted, and [`Headers.get()`](get) has been updated to fetch *all* header values instead of only the first one.

If the requested header doesn't exist in the `Headers` object, it returns an empty array.

For security reasons, some headers can only be controller by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

Syntax
------

    myHeaders.getAll(name);

### Parameters

*name*  
The name of the HTTP header whose values you want to retrieve from the `Headers` object. If the given name is not the name of an HTTP header, this method throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

### Returns

An <span class="page-not-created">`Array`</span> containing a [`ByteString`](../bytestring) sequence representing the values of the retrieved header.

Example
-------

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using [`Headers.append`](append), then retrieve it using `getAll()`:

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.getAll('Content-Type'); // Returns [ "image/jpeg" ]

If the header has multiple values associated with it, the array will contain all the values, in the order they were added to the Headers object:

    myHeaders.append('Accept-Encoding', 'deflate');
    myHeaders.append('Accept-Encoding', 'gzip');
    myHeaders.getAll('Accept-Encoding'); // Returns [ "deflate", "gzip" ]

**Note**: Use [`Headers.get`](get) to return only the first value added to the `Headers` object.

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

`getAll`

42-60

≤18-79

39-52

34

No

29-47

No

42-60

42-60

No

29-44

No

4.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/getAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/getAll</a>
