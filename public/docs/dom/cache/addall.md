# Cache.addAll()

The `addAll()` method of the [`Cache`](../cache) interface takes an array of URLs, retrieves them, and adds the resulting response objects to the given cache. The request objects created during retrieval become keys to the stored response operations.

**Note**: `addAll()` will overwrite any key/value pairs previously stored in the cache that match the request, but will fail if a resulting `put()` operation would overwrite a previous cache entry stored by the same `addAll()` method.

## Syntax

    cache.addAll(requests[]).then(function() {
      // requests have been added to the cache
    });

### Parameters

requests  
An array of string URLs that you want to be fetched and added to the cache. You can specify the [`Request`](../request) object instead of the URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with `undefined`.

### Exceptions

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th><strong>Exception</strong></th><th><strong>Happens when</strong></th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td><p>The URL scheme is not <code>http</code> or <code>https</code>.</p><p>The Response status is not in the 200 range (i.e., not a successful response.) This occurs if the request does not return successfully, but also if the request is a <em>cross-origin no-cors</em> request (in which case the reported status is always 0.)</p></td></tr></tbody></table>

## Examples

This code block waits for an [`InstallEvent`](../installevent) to fire, then runs [`waitUntil()`](../extendableevent/waituntil) to handle the install process for the app. This consists of calling [`CacheStorage.open`](../cachestorage/open) to create a new cache, then using `addAll()` to add a series of assets to it.

    this.addEventListener('install', function(event) {
      event.waitUntil(
        caches.open('v1').then(function(cache) {
          return cache.addAll([
            '/sw-test/',
            '/sw-test/index.html',
            '/sw-test/style.css',
            '/sw-test/app.js',
            '/sw-test/image-list.js',
            '/sw-test/star-wars-logo.jpg',
            '/sw-test/gallery/',
            '/sw-test/gallery/bountyHunters.jpg',
            '/sw-test/gallery/myLittleVader.jpg',
            '/sw-test/gallery/snowTroopers.jpg'
          ]);
        })
      );
    });

### Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cache-addAll">Service Workers<br />
<span class="small">The definition of 'Cache: addAll' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Using Service Workers](../service_worker_api/using_service_workers)
- [`Cache`](../cache)
- [`WorkerGlobalScope.caches`](../windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Cache/addAll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Cache/addAll</a>
