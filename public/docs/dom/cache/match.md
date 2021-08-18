# Cache.match()

The `match()` method of the [`Cache`](../cache) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the [`Response`](../response) associated with the first matching request in the [`Cache`](../cache) object. If no match is found, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Syntax

    cache.match(request, {options}).then(function(response) {
      // Do something with the response
    });

### Parameters

request  
The [`Request`](../request) for which you are attempting to find responses in the [`Cache`](../cache). This can be a [`Request`](../request) object or a URL.

options <span class="badge inline optional">Optional</span>  
An object that sets options for the `match` operation. The available options are:

- `ignoreSearch`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that specifies whether to ignore the query string in the URL. For example, if set to `true` the `?value=bar` part of `http://foo.com/?value=bar` would be ignored when performing a match. It defaults to `false`.
- `ignoreMethod`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that, when set to `true`, prevents matching operations from validating the [`Request`](../request) `http` method (normally only `GET` and `HEAD` are allowed.) It defaults to `false`.
- `ignoreVary`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that when set to `true` tells the matching operation not to perform `VARY` header matching — i.e. if the URL matches you will get a match regardless of whether the [`Response`](../response) object has a `VARY` header. It defaults to `false`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the first [`Response`](../response) that matches the request or to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if no match is found.

**Note**: `Cache.match()` is basically identical to [`Cache.matchAll()`](matchall), except that rather than resolving with an array of all matching responses, it resolves with the first matching response only (that is, `response[0]`).

## Examples

This example is taken from the [custom offline page](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/custom-offline-page/service-worker.js) example ([live demo](https://googlechrome.github.io/samples/service-worker/custom-offline-page/index.html)). It uses a cache to supply selected data when a request fails. A `catch()` clause is triggered when the call to `fetch()` throws an exception. Inside the `catch()` clause, `match()` is used to return the correct response.

In this example, only HTML documents retrieved with the GET HTTP verb will be cached. If our `if()` condition is false, then this fetch handler won't intercept the request. If there are any other fetch handlers registered, they will get a chance to call `event.respondWith()`. If no fetch handlers call `event.respondWith()`, the request will be handled by the browser as if there were no service worker involvement. If `fetch()` returns a valid HTTP response with an response code in the 4xx or 5xx range, the `catch()` will NOT be called.

    self.addEventListener('fetch', function(event) {
      // We only want to call event.respondWith() if this is a GET request for an HTML document.
      if (event.request.method === 'GET' &&
          event.request.headers.get('accept').indexOf('text/html') !== -1) {
        console.log('Handling fetch event for', event.request.url);
        event.respondWith(
          fetch(event.request).catch(function(e) {
            console.error('Fetch failed; returning offline page instead.', e);
            return caches.open(OFFLINE_CACHE).then(function(cache) {
              return cache.match(OFFLINE_URL);
            });
          })
        );
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-match">Service Workers<br />
<span class="small">The definition of 'Cache match' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/match</a>
