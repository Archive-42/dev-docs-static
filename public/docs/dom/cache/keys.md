# Cache.keys()

The `keys()` method of the [`Cache`](../cache) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`Cache`](../cache) keys.

The requests are returned in the same order that they were inserted.

**Note**: Requests with duplicate URLs but different headers can be returned if their responses have the `VARY` header set on them.

## Syntax

    cache.keys(request, {options}).then(function(keys) {
      // do something with your array of requests
    });

### Parameters

request <span class="badge inline optional">Optional</span>  
The [`Request`](../request) want to return, if a specific key is desired. This can be a `Request` object or a URL.

options <span class="badge inline optional">Optional</span>  
An object whose properties control how matching is done in the `keys` operation. The available options are:

- `ignoreSearch`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that specifies whether the matching process should ignore the query string in the url. If set to `true`, the `?value=bar` part of `http://foo.com/?value=bar` would be ignored when performing a match. It defaults to `false`.
- `ignoreMethod`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true`, prevents matching operations from validating the [`Request`](../request) `HTTP` method (normally only `GET` and `HEAD` are allowed.) It defaults to `false`.
- `ignoreVary`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true,` tells the matching operation not to perform `VARY` header matching. In other words, if the URL matches you will get a match regardless of whether the [`Response`](../response) object has a `VARY` header. It defaults to `false`.
- `cacheName`: A [`DOMString`](../domstring) that represents a specific cache to search within. Note that this option is ignored by `Cache.keys()`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`Cache`](../cache) keys.

## Examples

    caches.open('v1').then(function(cache) {
      cache.keys().then(function(keys) {
        keys.forEach(function(request, index, array) {
          cache.delete(request);
        });
      });
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-keys">Service Workers<br />
<span class="small">The definition of 'Cache: keys' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`keys`

43

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

30

11

43

43

39

30

11

4.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/keys" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/keys</a>
