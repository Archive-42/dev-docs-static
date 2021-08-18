# CacheStorage.open()

The `open()` method of the [`CacheStorage`](../cachestorage) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the [`Cache`](../cache) object matching the `cacheName`.

You can access `CacheStorage` through the global [`caches`](../windoworworkerglobalscope/caches) property.

**Note**: If the specified [`Cache`](../cache) does not exist, a new cache is created with that `cacheName` and a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to this new [`Cache`](../cache) object is returned.

## Syntax

    caches.open(cacheName).then(function(cache) {
      // Do something with your cache
    });

### Parameters

cacheName  
The name of the cache you want to open.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the requested [`Cache`](../cache) object.

## Examples

This example is from the MDN [sw-test example](https://github.com/mdn/sw-test/) (see [sw-test running live](https://mdn.github.io/sw-test/)). Here we wait for an [`InstallEvent`](../installevent) to fire, then runs [`waitUntil()`](../extendableevent/waituntil) to handle the install process for the app. This consists of calling `CacheStorage.open()` to create a new cache, then using [`Cache.addAll()`](../cache/addall) to add a series of assets to it.

    self.addEventListener('install', function(event) {
      event.waitUntil(
        caches.open('v1').then(function(cache) {
          return cache.addAll([
            '/sw-test/',
            '/sw-test/index.html',
            '/sw-test/style.css',
            '/sw-test/app.js',
            '/sw-test/image-list.js',
            '/sw-test/star-wars-logo.jpg',
            '/sw-test/gallery/bountyHunters.jpg',
            '/sw-test/gallery/myLittleVader.jpg',
            '/sw-test/gallery/snowTroopers.jpg'
          ]);
        })
      );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-storage-open">Service Workers<br />
<span class="small">The definition of 'CacheStorage: open' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`open`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage/open</a>
