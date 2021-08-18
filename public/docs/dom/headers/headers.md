# Headers()

The `Headers()` constructor creates a new [`Headers`](../headers) object.

## Syntax

    var myHeaders = new Headers(init);

### Parameters

`init` <span class="badge inline optional">Optional</span>  
An object containing any [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) that you want to pre-populate your `Headers` object with. This can be a simple object literal with [`ByteString`](../bytestring) values; or an existing `Headers` object. In the last case, the new `Headers` object copies its data from the existing `Headers` object.

## Example

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using [`Headers.append`](append):

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.get('Content-Type'); // Returns 'image/jpeg'

Or you can add the headers you want as the `Headers` object is created. In the following snippet we create a new [`Headers`](../headers) object, adding some headers by passing the constructor an init object as an argument:

    var httpHeaders = { 'Content-Type' : 'image/jpeg', 'X-My-Custom-Header' : 'Zeke are cool' };
    var myHeaders = new Headers(httpHeaders);

You can now create another `Headers` object, passing it the first `Headers` object as its init object:

    var secondHeadersObj = new Headers(myHeaders);
    secondHeadersObj.get('Content-Type'); // Would return 'image/jpeg' — it inherits it from the first headers object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers">Fetch<br />
<span class="small">The definition of 'Headers()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Headers`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/Headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/Headers</a>
