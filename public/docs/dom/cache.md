# Cache

The `Cache` interface provides a persistent storage mechanism for `Request` / `Response` object pairs that are cached in long lived memory. How long a Cache lives is browser dependent, but a single origin's scripts can typically rely on the presence of a previously populated Cache. Note that the `Cache` interface is exposed to windowed scopes as well as workers. You don't have to use it in conjunction with service workers, even though it is defined in the service worker spec.

An origin can have multiple, named `Cache` objects. You are responsible for implementing how your script (e.g. in a [`ServiceWorker`](serviceworker)) handles `Cache` updates. Items in a `Cache` do not get updated unless explicitly requested; they don’t expire unless deleted. Use [`CacheStorage.open()`](cachestorage/open) to open a specific named `Cache` object and then call any of the `Cache` methods to maintain the `Cache`.

You are also responsible for periodically purging cache entries. Each browser has a hard limit on the amount of cache storage that a given origin can use. Cache quota usage estimates are available via the [`StorageEstimate`](storageestimate) API. The browser does its best to manage disk space, but it may delete the Cache storage for an origin. The browser will generally delete all of the data for an origin or none of the data for an origin. Make sure to version caches by name and use the caches only from the version of the script that they can safely operate on. See [Deleting old caches](service_worker_api/using_service_workers#deleting_old_caches) for more information.

**Note**

The key matching algorithm depends on the [VARY header](https://www.fastly.com/blog/best-practices-for-using-the-vary-header) in the value. So matching a new key requires looking at both key and value for entries in the Cache.

**Note**

The caching API doesn't honor HTTP caching headers.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

## Methods

[`Cache.match(request, options)`](cache/match)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the response associated with the first matching request in the `Cache` object.

[`Cache.matchAll(request, options)`](cache/matchall)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of all matching requests in the `Cache` object.

[`Cache.add(request)`](cache/add)  
Takes a URL, retrieves it and adds the resulting response object to the given cache. This is functionally equivalent to calling `fetch()`, then using `put()` to add the results to the cache.

[`Cache.addAll(requests)`](cache/addall)  
Takes an array of URLs, retrieves them, and adds the resulting response objects to the given cache.

[`Cache.put(request, response)`](cache/put)  
Takes both a request and its response and adds it to the given cache.

[`Cache.delete(request, options)`](cache/delete)  
Finds the `Cache` entry whose key is the request, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if a matching `Cache` entry is found and deleted. If no `Cache` entry is found, the promise resolves to `false`.

[`Cache.keys(request, options)`](cache/keys)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of `Cache` keys.

## Examples

This code snippet is from the [service worker selective caching sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/selective-caching/service-worker.js). (see [selective caching live](https://googlechrome.github.io/samples/service-worker/selective-caching/)) The code uses [`CacheStorage.open()`](cachestorage/open) to open any `Cache` objects with a `Content-Type` header that starts with `font/`.

The code then uses [`Cache.match()`](cache/match) to see if there's already a matching font in the cache, and if so, returns it. If there isn't a matching font, the code fetches the font from the network and uses [`Cache.put()`](cache/put) to cache the fetched resource.

The code handles exceptions thrown from the [`fetch()`](windoworworkerglobalscope/fetch) operation. Note that an HTTP error response (e.g., 404) will not trigger an exception. It will return a normal response object that has the appropriate error code.

The code snippet also shows a best practice for versioning caches used by the service worker. Though there's only one cache in this example, the same approach can be used for multiple caches. It maps a shorthand identifier for a cache to a specific, versioned cache name. The code also deletes all caches that aren't named in `CURRENT_CACHES`.

In the code example, `caches` is a property of the [`ServiceWorkerGlobalScope`](serviceworkerglobalscope). It holds the `CacheStorage` object, by which it can access the [`CacheStorage`](cachestorage) interface. This is an implementation of the [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) mixin.

**Note**

In Chrome, visit `chrome://inspect/#service-workers` and click on the "inspect" link below the registered service worker to view logging statements for the various actions the `service-worker.js` script is performing.

    var CACHE_VERSION = 1;
    var CURRENT_CACHES = {
      font: 'font-cache-v' + CACHE_VERSION
    };

    self.addEventListener('activate', function(event) {
      // Delete all caches that aren't named in CURRENT_CACHES.
      // While there is only one cache in this example, the same logic will handle the case where
      // there are multiple versioned caches.
      var expectedCacheNamesSet = new Set(Object.values(CURRENT_CACHES));
      event.waitUntil(
        caches.keys().then(function(cacheNames) {
          return Promise.all(
            cacheNames.map(function(cacheName) {
              if (!expectedCacheNamesSet.has(cacheName)) {
                // If this cache name isn't present in the set of "expected" cache names, then delete it.
                console.log('Deleting out of date cache:', cacheName);
                return caches.delete(cacheName);
              }
            })
          );
        })
      );
    });

    self.addEventListener('fetch', function(event) {
      console.log('Handling fetch event for', event.request.url);

      event.respondWith(
        caches.open(CURRENT_CACHES.font).then(function(cache) {
          return cache.match(event.request).then(function(response) {
            if (response) {
              // If there is an entry in the cache for event.request, then response will be defined
              // and we can just return it. Note that in this example, only font resources are cached.
              console.log(' Found response in cache:', response);

              return response;
            }

            // Otherwise, if there is no entry in the cache for event.request, response will be
            // undefined, and we need to fetch() the resource.
            console.log(' No response for %s found in cache. About to fetch ' +
              'from network...', event.request.url);

            // We call .clone() on the request since we might use it in a call to cache.put() later on.
            // Both fetch() and cache.put() "consume" the request, so we need to make a copy.
            // (see https://developer.mozilla.org/en-US/docs/Web/API/Request/clone)
            return fetch(event.request.clone()).then(function(response) {
              console.log('  Response for %s from network is: %O',
                event.request.url, response);

              if (response.status < 400 &&
                  response.headers.has('content-type') &&
                  response.headers.get('content-type').match(/^font\//i)) {
                // This avoids caching responses that we know are errors (i.e. HTTP status code of 4xx or 5xx).
                // We also only want to cache responses that correspond to fonts,
                // i.e. have a Content-Type response header that starts with "font/".
                // Note that for opaque filtered responses (https://fetch.spec.whatwg.org/#concept-filtered-response-opaque)
                // we can't access to the response headers, so this check will always fail and the font won't be cached.
                // All of the Google Web Fonts are served off of a domain that supports CORS, so that isn't an issue here.
                // It is something to keep in mind if you're attempting to cache other resources from a cross-origin
                // domain that doesn't support CORS, though!
                // We call .clone() on the response to save a copy of it to the cache. By doing so, we get to keep
                // the original response object which we will return back to the controlled page.
                // (see https://developer.mozilla.org/en-US/docs/Web/API/Request/clone)
                console.log('  Caching the response to', event.request.url);
                cache.put(event.request, response.clone());
              } else {
                console.log('  Not caching the response to', event.request.url);
              }

              // Return the original response object, which will be used to fulfill the resource request.
              return response;
            });
          }).catch(function(error) {
            // This catch() will handle exceptions that arise from the match() or fetch() operations.
            // Note that a HTTP error response (e.g. 404) will NOT trigger an exception.
            // It will return a normal response object that has the appropriate error code set.
            console.error('  Error in fetch handler:', error);

            throw error;
          });
        })
      );
    });

### Storing cookies in Caches

The [Fetch API](fetch_api) requires [`Set-Cookie`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) headers to be stripped before returning a [`Response`](response) object from [`fetch()`](windoworworkerglobalscope). So a `Response` stored in a Cache won't contain headers.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache">Service Workers<br />
<span class="small">The definition of 'Cache' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Cache`

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

39

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11

4.0

`add`

44

Requires HTTPS from version 46.

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

31

Requires HTTPS from version 33.

11

44

Requires HTTPS from version 46.

44

Requires HTTPS from version 46.

39

32

Requires HTTPS from version 33.

11

4.0

Requires HTTPS from Samsung Internet 5.0.

`addAll`

46

Requires HTTPS.

16

39

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

33

Requires HTTPS.

11

46

Requires HTTPS.

46

Requires HTTPS.

39

33

Requires HTTPS.

11

5.0

Requires HTTPS.

`delete`

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

`worker_support`

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers.

No

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

44

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11

4.0

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [Service workers basic code example](https://github.com/mdn/sw-test)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Using web workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache</a>
