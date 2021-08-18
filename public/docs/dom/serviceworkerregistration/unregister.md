ServiceWorkerRegistration.unregister()
======================================

The `unregister()` method of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface unregisters the service worker registration and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). The promise will resolve to `false` if no registration was found, otherwise it resolves to `true` irrespective of whether unregistration happened or not (it may not unregister if someone else just called [`ServiceWorkerContainer.register()`](../serviceworkercontainer/register) with the same scope.) The service worker will finish any ongoing operations before it is unregistered.

**Note**: This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    serviceWorkerRegistration.unregister().then(function(boolean) {
    });

### Parameters

None.

### Return value

[`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves with a boolean indicating whether the service worker has unregistered or not.

Example
-------

The following simple example registers a service worker example, but then immediately unregisters it again:

    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('/sw-test/sw.js', {scope: 'sw-test'}).then(function(registration) {
        // registration worked
        console.log('Registration succeeded.');
        registration.unregister().then(function(boolean) {
          // if boolean = true, unregister is successful
        });
      }).catch(function(error) {
        // registration failed
        console.log('Registration failed with ' + error);
      });
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/navigator-service-worker-unregister">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.unregister()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unregister`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/unregister" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/unregister</a>
