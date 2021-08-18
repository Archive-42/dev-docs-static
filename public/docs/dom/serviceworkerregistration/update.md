ServiceWorkerRegistration.update()
==================================

The `update()` method of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface attempts to update the service worker. It fetches the worker's script URL, and if the new worker is not byte-by-byte identical to the current worker, it installs the new worker. The fetch of the worker bypasses any browser caches if the previous fetch occurred over 24 hours ago.

**Note**: This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    serviceWorkerRegistration.update();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`ServiceWorkerRegistration`](../serviceworkerregistration) object.

Example
-------

The following simple example registers a service worker example then adds an event handler to a button so you can explicitly update the service worker whenever desired:

    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('/sw-test/sw.js', {scope: 'sw-test'}).then(function(registration) {
        // registration worked
        console.log('Registration succeeded.');
        button.onclick = function() {
          registration.update();
        }
      }).catch(function(error) {
        // registration failed
        console.log('Registration failed with ' + error);
      });
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-registration-update">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.update()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`update`

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

\["Starting with Opera 33, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Opera 35, this method always bypassed the browser cache. Starting with Opera 35, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

11.1

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

45

\["Starting with Chrome 46, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Chrome 48, this method always bypassed the browser cache. Starting with Chrome 48, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

44

32

\["Starting with Opera 33, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Opera 35, this method always bypassed the browser cache. Starting with Opera 35, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

No

4.0

\["Starting with Samsung Internet 5.0, update() returns a promise that resolves with 'undefined' if the operation completed successfully or there was no update, and rejects if update failed. If the new worker ran but installation failed, the promise still resolves. Formerly, it raised an exception.", "Before Samsung Internet 5.0, this method always bypassed the browser cache. Starting with Samsung Internet 5.0, it only bypasses the cache when the previous service worker check was more than twenty-four hours ago."\]

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/update" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/update</a>
