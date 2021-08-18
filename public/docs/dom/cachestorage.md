# CacheStorage

The `CacheStorage` interface represents the storage for [`Cache`](cache) objects.

The interface:

- Provides a master directory of all the named caches that can be accessed by a [`ServiceWorker`](serviceworker) or other type of worker or [`window`](window) scope (you’re not limited to only using it with service workers, even though the [Service Workers](https://w3c.github.io/ServiceWorker/) spec defines it).
  **Note**
  [Chrome and Safari only expose \`CacheStorage\` to the windowed context over HTTPS](https://bugs.chromium.org/p/chromium/issues/detail?id=1026063). [`WorkerGlobalScope.caches`](windoworworkerglobalscope/caches) will be undefined unless an SSL certificate is configured.

- Maintains a mapping of string names to corresponding [`Cache`](cache) objects.

Use [`CacheStorage.open()`](cachestorage/open) to obtain a [`Cache`](cache) instance.

Use [`CacheStorage.match()`](cachestorage/match) to check if a given [`Request`](request) is a key in any of the [`Cache`](cache) objects that the `CacheStorage` object tracks.

You can access `CacheStorage` through the global [`caches`](windoworworkerglobalscope/caches) property.

**Note**

CacheStorage always rejects with a `SecurityError` on untrusted origins (i.e. those that aren't using HTTPS, although this definition will likely become more complex in the future.) When testing on Firefox, you can get around this by checking the **Enable Service Workers over HTTP (when toolbox is open)** option in the Firefox Devtools options/gear menu.

**Note**

[`CacheStorage.match()`](cachestorage/match) is a convenience method. Equivalent functionality to match a cache entry can be implemented by returning an array of cache names from [`CacheStorage.keys()`](cachestorage/keys), opening each cache with [`CacheStorage.open()`](cachestorage/open), and matching the one you want with [`Cache.match()`](cache/match).

**Note:** This feature is available in [Web Workers](web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

## Methods

[`CacheStorage.match()`](cachestorage/match)  
Checks if a given [`Request`](request) is a key in any of the [`Cache`](cache) objects that the [`CacheStorage`](cachestorage) object tracks, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to that match.

[`CacheStorage.has()`](cachestorage/has)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true` if a [`Cache`](cache) object matching the `cacheName` exists.

[`CacheStorage.open()`](cachestorage/open)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the [`Cache`](cache) object matching the `cacheName` (a new cache is created if it doesn't already exist.)

[`CacheStorage.delete()`](cachestorage/delete)  
Finds the [`Cache`](cache) object matching the `cacheName`, and if found, deletes the [`Cache`](cache) object and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to `true`. If no [`Cache`](cache) object is found, it resolves to `false`.

[`CacheStorage.keys()`](cachestorage/keys)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will resolve with an array containing strings corresponding to all of the named [`Cache`](cache) objects tracked by the [`CacheStorage`](cachestorage). Use this method to iterate over a list of all the [`Cache`](cache) objects.

## Examples

This code snippet is from the MDN [sw-test example](https://github.com/mdn/sw-test/) (see [sw-test running live](https://mdn.github.io/sw-test/).) This service worker script waits for an [`InstallEvent`](installevent) to fire, then runs [`waitUntil`](extendableevent/waituntil) to handle the install process for the app. This consists of calling [`CacheStorage.open`](cachestorage/open) to create a new cache, then using [`Cache.addAll`](cache/addall) to add a series of assets to it.

In the second code block, we wait for a [`FetchEvent`](fetchevent) to fire. We construct a custom response like so:

1.  Check whether a match for the request is found in the CacheStorage. If so, serve that.
2.  If not, fetch the request from the network, then also open the cache created in the first block and add a clone of the request to it using [`Cache.put`](cache/put) (`cache.put(event.request, response.clone())`.)
3.  If this fails (e.g. because the network is down), return a fallback response.

Finally, return whatever the custom response ended up being equal to, using [`FetchEvent.respondWith`](fetchevent/respondwith).

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
    });

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

This snippet shows how the API can be used outside of a service worker context, and uses the `await` operator for much more readable code.

    // Try to get data from the cache, but fall back to fetching it live.
    async function getData() {
       const cacheVersion = 1;
       const cacheName    = `myapp-${ cacheVersion }`;
       const url          = 'https://jsonplaceholder.typicode.com/todos/1';
       let cachedData     = await getCachedData( cacheName, url );

       if ( cachedData ) {
          console.log( 'Retrieved cached data' );
          return cachedData;
       }

       console.log( 'Fetching fresh data' );

       const cacheStorage = await caches.open( cacheName );
       await cacheStorage.add( url );
       cachedData = await getCachedData( cacheName, url );
       await deleteOldCaches( cacheName );

       return cachedData;
    }

    // Get data from the cache.
    async function getCachedData( cacheName, url ) {
       const cacheStorage   = await caches.open( cacheName );
       const cachedResponse = await cacheStorage.match( url );

       if ( ! cachedResponse || ! cachedResponse.ok ) {
          return false;
       }

       return await cachedResponse.json();
    }

    // Delete any old caches to respect user's disk space.
    async function deleteOldCaches( currentCache ) {
       const keys = await caches.keys();

       for ( const key of keys ) {
          const isOurCache = 'myapp-' === key.substr( 0, 6 );

          if ( currentCache === key || ! isOurCache ) {
             continue;
          }

          caches.delete( key );
       }
    }

    try {
       const data = await getData();
       console.log( { data } );
    } catch ( error ) {
       console.error( { error } );
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#cachestorage">Service Workers<br />
<span class="small">The definition of 'CacheStorage' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CacheStorage`

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

16

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11.1

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported

44

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11.3

4.0

`delete`

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

`keys`

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

`secure_context_required`

65

≤79

44

No

52

Yes

65

65

44

47

Yes

9.0

`worker_support`

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers.

No

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11.1

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

40

Before version 43, only service workers are supported. From version 43, all worker types and the main thread are supported.

44

27

Before version 30, only service workers are supported. From version 30, all worker types and the main thread are supported.

11.3

4.0

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [`Cache`](cache)
- [`WindowOrWorkerGlobalScope.caches`](windoworworkerglobalscope/caches)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CacheStorage</a>
