ServiceWorkerGlobalScope.onactivate
===================================

The **onactivate** property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is an event handler fired whenever an `activate` event occurs (when the service worker activates). This happens after installation, when the page to be controlled by the service worker refreshes.

Syntax
------

    ServiceWorkerGlobalScope.onactivate = function(event) { ... };

Examples
--------

The following snippet shows how you could use an `activate` event handler to upgrade a cache.

    then.addEventListener('activate', function(event) {
      var cacheWhitelist = ['v2'];

      event.waitUntil(
        caches.forEach(function(cache, cacheName) {
          if (cacheWhitelist.indexOf(cacheName) == -1) {
            return caches.delete(cacheName);
          }
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

`onactivate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onactivate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/onactivate</a>
