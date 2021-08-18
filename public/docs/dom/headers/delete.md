# Headers.delete()

The `delete()` method of the [`Headers`](../headers) interface deletes a header from the current `Headers` object.

This method throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) for the following reasons:

- The value of the name parameter is not the name of an HTTP header.
- The value of [Guard](https://developer.mozilla.org/en-US/docs/Glossary/Guard) is `immutable`.

For security reasons, some headers can only be controller by the user agent. These headers include the [forbidden header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) and [forbidden response header names](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name).

## Syntax

    myHeaders.delete(name);

### Parameters

`name`  
The name of the HTTP header you want to delete from the `Headers` object.

### Returns

Void.

## Example

Creating an empty `Headers` object is simple:

    var myHeaders = new Headers(); // Currently empty

You could add a header to this using [`Headers.append`](append):

    myHeaders.append('Content-Type', 'image/jpeg');
    myHeaders.get('Content-Type'); // Returns 'image/jpeg'

You can then delete it again:

    myHeaders.delete('Content-Type');
    myHeaders.get('Content-Type'); // Returns null, as it has been deleted

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-headers-delete">Fetch<br />
<span class="small">The definition of 'delete()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`delete`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Headers/delete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Headers/delete</a>
