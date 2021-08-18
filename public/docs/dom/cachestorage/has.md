# CacheStorage.has()

The `has()` method of the [`CacheStorage`](../cachestorage) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if a [`Cache`](../cache) object matches the `cacheName`.

You can access `CacheStorage` through the global [`caches`](../windoworworkerglobalscope/caches) property.

## Syntax

    caches.has(cacheName).then(function(boolean) {
      // true: your cache exists!
    });

### Parameters

`cacheName`  
A [`DOMString`](../domstring) representing the name of the [`Cache`](../cache) object you are looking for in the [`CacheStorage`](../cachestorage).

### Return value

a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if the cache exists or `false` if not.

## Examples

The following example first checks whether a cache called 'v1' exists. If so, we add a list of assets to it. If not then we run some kind of cache set-up function.

    caches.has('v1').then(function(hasCache) {
      if (!hasCache) {
        someCacheSetupFunction();
      } else {
        caches.open('v1').then(function(cache) {
          return cache.addAll(myAssets);
        });
      }
    }).catch(function() {
      // Handle exception here.
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-storage-has">Service Workers<br />
<span class="small">The definition of 'CacheStorage: has' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`has`

40

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

Yes

4.0

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WindowOrWorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/has" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/has</a>
