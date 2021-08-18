ServiceWorkerGlobalScope.skipWaiting()
======================================

The `ServiceWorkerGlobalScope.skipWaiting()` method of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) forces the waiting service worker to become the active service worker.

Use this method with [`Clients.claim()`](../clients/claim) to ensure that updates to the underlying service worker take effect immediately for both the current client and all other active clients.

Syntax
------

    ServiceWorkerGlobalScope.skipWaiting().then(function() {
      //Do something
    });

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that immediately resolves with `undefined`.

Example
-------

While `self.skipWaiting()` can be called at any point during the service worker's execution, it will only have an effect if there's a newly installed service worker that might otherwise remain in the `waiting` state. Therefore, it's common to call `self.skipWaiting()` from inside of an [`InstallEvent`](../installevent) handler.

The following example causes a newly installed service worker to progress into the `activating` state, regardless of whether there is already an active service worker.

    self.addEventListener('install', function(event) {
      // The promise that skipWaiting() returns can be safely ignored.
      self.skipWaiting();

      // Perform any other actions required for your
      // service worker to install, potentially inside
      // of event.waitUntil();
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkerglobalscope-skipwaiting">Service Workers<br />
<span class="small">The definition of 'skipWaiting()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`skipWaiting`

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
-   [`Clients.claim()`](../clients/claim)
-   [`Promises`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/skipWaiting</a>
