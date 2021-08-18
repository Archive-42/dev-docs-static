# Body.formData()

The `formData()` method of the [`Body`](../body) mixin takes a [`Response`](../response) stream and reads it to completion. It returns a promise that resolves with a [`FormData`](../formdata) object.

**Note**: This is mainly relevant to [service workers](../service_worker_api). If a user submits a form and a service worker intercepts the request, you could for example call `formData()` on it to obtain a key-value map, modify some fields, then send the form onwards to the server (or use it locally).

## Syntax

    response.formData()
    .then(function(formdata) {
      // do something with your formdata
    });

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`FormData`](../formdata) object.

## Example

TBD.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-formdata">Fetch<br />
<span class="small">The definition of 'formData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`formData`

60

≤79

39

No

47

10.1

From Safari 10.1, the method exists but always rejects with `NotSupportedError`. See [bug 215671](https://webkit.org/b/215671).

60

60

No

44

10.3

From Safari for iOS 10.3, the method exists but always rejects with `NotSupportedError`. See [bug 215671](https://webkit.org/b/215671).

8.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/formData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/formData</a>
