# Headers.has()

The `has()` method of the [`Headers`](../headers) interface returns a boolean stating whether a `Headers` object contains a certain header.

For security reasons, some headers can only be controlled by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

## Syntax

    myHeaders.has(name);

### Parameters

`name`  
The name of the HTTP header you want to test for. If the given name is not a valid HTTP header name, this method throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Example

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using [`Headers.append`](append), then test for the existence of it using `has()`:

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.has('Content-Type'); // Returns true
    myHeaders.has('Accept-Encoding'); // Returns false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers-has">Fetch<br />
<span class="small">The definition of 'has()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`has`

42

41

14

39

34

No

29

28

10.1

42

42

41

No

29

28

10.3

4.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/has</a>
