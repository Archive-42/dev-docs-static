# Cache.matchAll()

The `matchAll()` method of the [`Cache`](../cache) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of all matching responses in the [`Cache`](../cache) object.

## Syntax

    cache.matchAll(request, {options}).then(function(response) {
      // do something with the response array
    });

### Parameters

request <span class="badge inline optional">Optional</span>  
The [`Request`](../request) for which you are attempting to find responses in the [`Cache`](../cache). This can be a `Request` object or a URL. If this argument is omitted, you will get a copy of all responses in this cache.

options <span class="badge inline optional">Optional</span>  
An options object allowing you to set specific control options for the matching performed. The available options are:

- `ignoreSearch`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that specifies whether the matching process should ignore the query string in the url. If set to `true`, the `?value=bar` part of `http://foo.com/?value=bar` would be ignored when performing a match. It defaults to `false`.
- `ignoreMethod`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true`, prevents matching operations from validating the [`Request`](../request) `http` method (normally only `GET` and `HEAD` are allowed.) It defaults to `false`.
- `ignoreVary`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that when set to `true` tells the matching operation not to perform `VARY` header matching — i.e. if the URL matches you will get a match regardless of the [`Response`](../response) object having a `VARY` header or not. It defaults to `false`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of all matching responses in the [`Cache`](../cache) object.

**Note**: [`Cache.match()`](match) is basically identical to `Cache.matchAll()`, except that rather than resolving with an array of all matching responses, it resolves with the first matching response only (that is, `response[0]`).

## Examples

    caches.open('v1').then(function(cache) {
      cache.matchAll('/images/').then(function(response) {
        response.forEach(function(element, index, array) {
          cache.delete(element);
        });
      });
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-matchall">Service Workers<br />
<span class="small">The definition of 'Cache: matchAll' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`matchAll`

47

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

34

Requires HTTPS.

11

47

47

39

34

11

5.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/matchAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/matchAll</a>
