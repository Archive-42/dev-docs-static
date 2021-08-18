NavigationPreloadManager
========================

The `NavigationPreloadManager` interface of the [Service Worker API](service_worker_api) provides methods for managing the preloading of resources with a service worker.

Methods
-------

<span class="page-not-created">`NavigationPreloadManager.enable()`</span>  
Enables navigation preloading and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves.

<span class="page-not-created">`NavigationPreloadManager.disable()`</span>  
Disables navigation preloading and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves.

<span class="page-not-created">`NavigationPreloadManager.setHeaderValue()`</span>  
Sets the value of the `Service-Worker-Navigation-Preload` header and returns an empty [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

<span class="page-not-created">`NavigationPreloadManager.getState()`</span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an object with properties indicating whether preload is enabled and the contents of the `Service-Worker-Navigation-Preload`.

Examples
--------

#### Feature Detecting and Enabling Navigation Preloading

    addEventListener('activate', event => {
      event.waitUntil(async function() {
        if (self.registration.navigationPreload) {
          // Enable navigation preloads!
          await self.registration.navigationPreload.enable();
        }
      }());
    });

#### Using a Preloaded Response

The following example shows the implementation of a fetch event that uses a preloaded response.

    addEventListener('fetch', event => {
      event.respondWith(async function() {
        // Respond from the cache if we can
        const cachedResponse = await caches.match(event.request);
        if (cachedResponse) return cachedResponse;

        // Else, use the preloaded response, if it's there
        const response = await event.preloadResponse;
        if (response) return response;

        // Else try the network.
        return fetch(event.request);
      }());
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigation-preload-manager">Service Workers<br />
<span class="small">The definition of 'NavigationPreloadManager' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`NavigationPreloadManager`

62

18

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

No

49

No

62

62

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

46

No

8.0

`disable`

62

18

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

No

49

No

62

62

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

46

No

8.0

`enable`

62

18

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

No

49

No

62

62

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

46

No

8.0

`getState`

62

18

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

No

49

No

62

62

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

46

No

8.0

`setHeaderValue`

62

18

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

No

49

No

62

62

No

Implementation tracked in [bug 1290958](https://bugzil.la/1290958)

46

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigationPreloadManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigationPreloadManager</a>
