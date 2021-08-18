ServiceWorkerGlobalScope.onfetch
================================

The **onfetch** property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is an event handler fired whenever a `fetch` event occurs (usually when the [`WindowOrWorkerGlobalScope.fetch()`](../windoworworkerglobalscope/fetch) method is called.)

Syntax
------

    serviceWorkerGlobalScope.onfetch = function(fetchEvent) { ... };

Example
-------

This code snippet is from the [service worker prefetch sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/prefetch/service-worker.js) (see [prefetch example live](https://googlechrome.github.io/samples/service-worker/prefetch/).) The [`ServiceWorkerGlobalScope.onfetch`](onfetch) event handler listens for the `fetch` event. When fired, the code returns a promise that resolves to the first matching request in the [`Cache`](../cache) object. If no match is found, the code fetches a response from the network.

The code also handles exceptions thrown from the [`fetch()`](../windoworworkerglobalscope/fetch) operation. Note that an HTTP error response (e.g., 404) will not trigger an exception. It will return a normal response object that has the appropriate error code set.

    self.addEventListener('fetch', function(event) {
      console.log('Handling fetch event for', event.request.url);

      event.respondWith(
        caches.match(event.request).then(function(response) {
          if (response) {
            console.log('Found response in cache:', response);

            return response;
          }
          console.log('No response found in cache. About to fetch from network...');

          return fetch(event.request).then(function(response) {
            console.log('Response from network is:', response);

            return response;
          }).catch(function(error) {
            console.error('Fetching failed:', error);

            throw error;
          });
        })
      );
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-event-handlers">Service Workers<br />
<span class="small">The definition of 'Event Handlers' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onfetch`

40

≤79

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

24

11.1

40

40

44

24

11.3

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onfetch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onfetch</a>
