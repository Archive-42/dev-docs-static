# Headers.set()

The `set()` method of the [`Headers`](../headers) interface sets a new value for an existing header inside a `Headers` object, or adds the header if it does not already exist.

The difference between `set()` and [`Headers.append`](append) is that if the specified header already exists and accepts multiple values, `set()` overwrites the existing value with the new one, whereas [`Headers.append`](append) appends the new value to the end of the set of values.

For security reasons, some headers can only be controller by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

## Syntax

    myHeaders.set(name, value);

### Parameters

`name`  
The name of the HTTP header you want to set to a new value. If the given name is not the name of an HTTP header, this method throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

`value`  
The new value you want to set.

### Returns

Void.

## Example

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using [`Headers.append`](append), then set a new value for this header using `set()`:

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.set('Content-Type', 'text/html');

If the specified header does not already exist, `set()` will create it and set its value to the specified value. If the specified header does already exist and does accept multiple values, `set()` will overwrite the existing value with the new one:

    myHeaders.set('Accept-Encoding', 'deflate');
    myHeaders.set('Accept-Encoding', 'gzip');
    myHeaders.get('Accept-Encoding'); // Returns 'gzip'

You'd need [`Headers.append`](append) to append the new value onto the values, not overwrite it.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers-set">Fetch<br />
<span class="small">The definition of 'set()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`set`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/set</a>
