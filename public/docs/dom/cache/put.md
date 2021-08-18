# Cache.put()

The `put()` method of the [`Cache`](../cache) interface allows key/value pairs to be added to the current [`Cache`](../cache) object.

Often, you will just want to [`fetch()`](../windoworworkerglobalscope/fetch) one or more requests, then add the result straight to your cache. In such cases you are better off using [`Cache.add()`](add)/[`Cache.addAll()`](addall), as they are shorthand functions for one or more of these operations.

    fetch(url).then(function(response) {
      if (!response.ok) {
        throw new TypeError('Bad response status');
      }
      return cache.put(url, response);
    })

**Note**: `put()` will overwrite any key/value pair previously stored in the cache that matches the request.

**Note**: [`Cache.add`](add)/[`Cache.addAll`](addall) do not cache responses with `Response.status` values that are not in the 200 range, whereas [`Cache.put`](put) lets you store any request/response pair. As a result, [`Cache.add`](add)/[`Cache.addAll`](addall) can't be used to store opaque responses, whereas [`Cache.put`](put) can.

## Syntax

    cache.put(request, response).then(function() {
      // request/response pair has been added to the cache
    });

### Parameters

request  
The [`Request`](../request) object or URL that you want to add to the cache.

response  
The [`Response`](../response) you want to match up to the request.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`.

**Note**: The promise will reject with a `TypeError` if the URL scheme is not `http` or `https`.

## Examples

This example is from the MDN [sw-test example](https://github.com/mdn/sw-test/) (see [sw-test running live](https://mdn.github.io/sw-test/)). Here we wait for a [`FetchEvent`](../fetchevent) to fire. We construct a custom response like so:

1.  Check whether a match for the request is found in the [`CacheStorage`](../cachestorage) using [`CacheStorage.match()`](../cachestorage/match). If so, serve that.
2.  If not, open the `v1` cache using `open()`, put the default network request in the cache using [`Cache.put()`](put) and return a clone of the default network request using `return response.clone()`. Clone is needed because `put()` consumes the response body.
3.  If this fails (e.g., because the network is down), return a fallback response.

<!-- -->

    var response;
    var cachedResponse = caches.match(event.request).catch(function() {
      return fetch(event.request);
    }).then(function(r) {
      response = r;
      caches.open('v1').then(function(cache) {
        cache.put(event.request, response);
      });
      return response.clone();
    }).catch(function() {
      return caches.match('/sw-test/gallery/myLittleVader.jpg');
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-put">Service Workers<br />
<span class="small">The definition of 'Cache: put' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`put`

43

Requires HTTPS from version 46.

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

30

Requires HTTPS from version 33.

11

43

Requires HTTPS from version 46.

43

Requires HTTPS from version 46.

39

30

Requires HTTPS from version 33.

11

4.0

Requires HTTPS from Samsung Internet 5.0.

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/put" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/put</a>
