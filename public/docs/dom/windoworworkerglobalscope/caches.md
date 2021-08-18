WindowOrWorkerGlobalScope.caches
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `caches` read-only property of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) interface returns the [`CacheStorage`](../cachestorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

Syntax
------

    var myCacheStorage = self.caches; // or just caches

### Value

A [`CacheStorage`](../cachestorage) object.

Example
-------

The following example shows how you'd use a cache in a [service worker](../service_worker_api) context to store assets offline.

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#self-caches">Service Workers<br />
<span class="small">The definition of 'caches' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defined in a <code>WindowOrWorkerGlobalScope</code> partial in the newest spec.</td></tr><tr class="even"><td><a href="https://w3c.github.io/ServiceWorker/">Service Workers</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`caches`

40

≤79

42

No

?

No

40

Yes

42

Yes

Yes

Yes

See also
--------

-   [Service Workers](../service_worker_api)
-   [Web Workers](../web_workers_api)
-   [`CacheStorage`](../cachestorage)
-   [`Cache`](../cache)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/caches</a>
