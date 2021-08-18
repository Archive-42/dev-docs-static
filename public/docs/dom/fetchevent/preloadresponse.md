FetchEvent.preloadResponse
==========================

The `preloadResponse` read-only property of the [`FetchEvent`](../fetchevent) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the navigation preload [`Response`](../response) if navigation preload was triggered or undefined otherwise.

Syntax
------

    var expectedResponse = fetchEvent.preloadResponse;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Response`](../response) or otherwise to `undefined`.

Example
-------

This code snippet is from the [navigation preload page](https://developers.google.com/web/updates/2017/02/navigation-preload#the-solution). The [`ServiceWorkerGlobalScope.onfetch`](../serviceworkerglobalscope/onfetch) event handler listens for the `fetch` event. When fired, pass a promise that back to the controlled page to [`FetchEvent.respondWith()`](respondwith). This promise resolves to the first matching URL request in the [`Cache`](../cache) object. If no match is found, the code checks for a preloaded response. Else it fetches a response from the network.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#fetch-event-preloadresponse">Service Workers<br />
<span class="small">The definition of 'preloadResponse' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PreloadResponse`

59

18

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

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/PreloadResponse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/PreloadResponse</a>
