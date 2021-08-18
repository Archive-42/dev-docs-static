ServiceWorkerGlobalScope.oninstall
==================================

The `oninstall` property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is an event handler fired whenever an [`install`](install_event) event occurs (when the service worker installs). This happens before [activation](activate_event).

Syntax
------

    self.oninstall = function(event) { ... };

Examples
--------

The following snippet shows how an `install` event handler can be used to populate a cache with a number of responses, which the service worker can then use to serve assets offline:

    self.oninstall = function(event) {
      event.waitUntil(
       caches.open('v1').then(function(cache) {
             return cache.add(
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
         );
       })
       );
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-event-handlers">Service Workers<br />
<span class="small">The definition of 'Event Handlers' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`oninstall`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/oninstall" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/oninstall</a>
