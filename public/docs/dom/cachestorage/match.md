# CacheStorage.match()

The `match()` method of the [`CacheStorage`](../cachestorage) interface checks if a given [`Request`](../request) or url string is a key for a stored [`Response`](../response). This method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a [`Response`](../response), or a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to `undefined` if no match is found.

You can access `CacheStorage` through the global [`caches`](../windoworworkerglobalscope/caches) property.

`Cache` objects are searched in creation order.

**Note**: [`caches.match()`](match) is a convenience method. Equivalent functionality is to call [`cache.match()`](../cache/match) on each cache (in the order returned by [`caches.keys()`](keys)) until a [`Response`](../response) is returned.

## Syntax

    caches.match(request, options).then(function(response) {
      // Do something with the response
    });

### Parameters

request  
The [`Request`](../request) you want to match. This can be a [`Request`](../request) object or a URL string.

options <span class="badge inline optional">Optional</span>  
An object whose properties control how matching is done in the `match` operation. The available options are:

- `ignoreSearch`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that specifies whether the matching process should ignore the query string in the url. For example, if set to `true`, the `?value=bar` part of `http://foo.com/?value=bar` would be ignored when performing a match. It defaults to `false`.
- `ignoreMethod`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true`, prevents matching operations from validating the [`Request`](../request) `http` method (normally only `GET` and `HEAD` are allowed.) It defaults to `false`.
- `ignoreVary`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true,` tells the matching operation not to perform `VARY` header matching. In other words, if the URL matches you will get a match regardless of whether the [`Response`](../response) object has a `VARY` header or not. It defaults to `false`.
- `cacheName`: A [`DOMString`](../domstring) that represents a specific cache to search within.

### Return value

a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the matching [`Response`](../response). If no matching response to the specified request is found, the promise resolves with `undefined`.

## Examples

This example is from the MDN [sw-test example](https://github.com/mdn/sw-test/) (see [sw-test running live](https://mdn.github.io/sw-test/)). Here we wait for a [`FetchEvent`](../fetchevent) to fire. We construct a custom response like so:

1.  Check whether a match for the request is found in the [`CacheStorage`](../cachestorage) using [`CacheStorage.match()`](match). If so, serve that.
2.  If not, open the `v1` cache using `open()`, put the default network request in the cache using [`Cache.put()`](../cache/put) and return a clone of the default network request using `return response.clone()`. The last is necessary because `put()` consumes the response body.
3.  If this fails (e.g., because the network is down), return a fallback response.

<!-- -->

    self.addEventListener('fetch', function(event) {
      event.respondWith(caches.match(event.request).then(function(response) {
        // caches.match() always resolves
        // but in case of success response will have value
        if (response !== undefined) {
          return response;
        } else {
          return fetch(event.request).then(function (response) {
            // response may be used only once
            // we need to save clone to put one copy in cache
            // and serve second one
            let responseClone = response.clone();

            caches.open('v1').then(function (cache) {
              cache.put(event.request, responseClone);
            });
            return response;
          }).catch(function () {
            return caches.match('/sw-test/gallery/myLittleVader.jpg');
          });
        }
      }));
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-storage-match">Service Workers<br />
<span class="small">The definition of 'CacheStorage: match' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`match`

54

40

The options parameter only supports `ignoreSearch`, and `cacheName`.

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

41

27

The options parameter only supports `ignoreSearch`, and `cacheName`.

11.1

54

40

The options parameter only supports `ignoreSearch`, and `cacheName`.

54

40

The options parameter only supports `ignoreSearch`, and `cacheName`.

44

41

27

The options parameter only supports `ignoreSearch`, and `cacheName`.

Yes

6.0

4.0

The options parameter only supports `ignoreSearch`, and `cacheName`.

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WindowOrWorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/match</a>
