ServiceWorkerGlobalScope: activate event
========================================

The `activate` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface is fired when a [`ServiceWorkerRegistration`](../serviceworkerregistration) acquires a new [`ServiceWorkerRegistration.active`](../serviceworkerregistration/active) worker.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../extendableevent"><code>ExtendableEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onactivate"><code>ServiceWorkerGlobalScope.onactivate</code></a></td></tr></tbody></table>

Examples
--------

The following snippet shows how you could use an `activate` event handler to upgrade a cache.

    globalScope.addEventListener('activate', function(event) {
      var cacheWhitelist = ['v2'];

      event.waitUntil(
        caches.forEach(function(cache, cacheName) {
          if (cacheWhitelist.indexOf(cacheName) == -1) {
            return caches.delete(cacheName);
          }
        })
      );
    });

You can also set up the event handler using the [`ServiceWorkerGlobalScope.onactivate`](onactivate) property:

    globalScope.onactivate = function(event) {
      ...
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-activate-event">Service Workers<br />
<span class="small">The definition of 'activate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`activate_event`

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

-   [`install`](install_event) event
-   [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope)
-   [Service Worker API](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/activate_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/activate_event</a>
