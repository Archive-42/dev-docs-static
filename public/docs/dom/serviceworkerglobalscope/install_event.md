ServiceWorkerGlobalScope: install event
=======================================

The `install` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is fired when a [`ServiceWorkerRegistration`](../serviceworkerregistration) acquires a new [`ServiceWorkerRegistration.installing`](../serviceworkerregistration/installing) worker.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../extendableevent"><code>ExtendableEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="oninstall"><code>ServiceWorkerGlobalScope.oninstall</code></a></td></tr></tbody></table>

Examples
--------

The following snippet shows how an `install` event handler can be used to populate a cache with a number of responses, which the service worker can then use to serve assets offline:

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
          ])
       })
       );
    });

You can also set up the event handler using the [`ServiceWorkerGlobalScope.oninstall`](oninstall) property:

    globalScope.oninstall = function(event) {
      ...
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-install-event">Service Workers<br />
<span class="small">The definition of 'install' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`install_event`

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

-   [`activate`](activate_event) event
-   [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope)
-   [Service Worker API](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/install_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/install_event</a>
