FetchEvent.navigationPreload
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `navigationPreload` read-only property of the [`FetchEvent`](../fetchevent) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the instance of [`NavigationPreloadManager`](../navigationpreloadmanager) associated with the current service worker registration.

Syntax
------

    var promise = fetchEvent.navigationPreload

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the instance of [`NavigationPreloadManager`](../navigationpreloadmanager).

Example
-------

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-registration-navigationpreload">Service Workers<br />
<span class="small">The definition of 'navigationPreload' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`navigationPreload`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/navigationPreload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/navigationPreload</a>
