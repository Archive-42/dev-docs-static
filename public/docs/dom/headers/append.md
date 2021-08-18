# Headers.append()

The `append()` method of the [`Headers`](../headers) interface appends a new value onto an existing header inside a `Headers` object, or adds the header if it does not already exist.

The difference between [`set()`](set) and `append()` is that if the specified header already exists and accepts multiple values, `set()` will overwrite the existing value with the new one, whereas `append()` will append the new value onto the end of the set of values.

For security reasons, some headers can only be controlled by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

## Syntax

    myHeaders.append(name, value);

### Parameters

`name`  
The name of the HTTP header you want to add to the `Headers` object.

`value`  
The value of the HTTP header you want to add.

### Returns

Void.

## Example

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using `append()`:

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.get('Content-Type'); // Returns 'image/jpeg'

If the specified header already exists, `append()` will change its value to the specified value. If the specified header already exists and accepts multiple values, `append()` will append the new value to the end of the value set:

    myHeaders.append('Accept-Encoding', 'deflate');
    myHeaders.append('Accept-Encoding', 'gzip');
    myHeaders.get('Accept-Encoding'); // Returns 'deflate, gzip'

To overwrite the old value with a new one, use [`Headers.set`](set).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers-append">Fetch<br />
<span class="small">The definition of 'append()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`append`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/append</a>
