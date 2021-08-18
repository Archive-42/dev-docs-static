ServiceWorkerContainer.ready
============================

The `ready` read-only property of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface provides a way of delaying code execution until a service worker is active. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will never reject, and which waits indefinitely until the [`ServiceWorkerRegistration`](../serviceworkerregistration) associated with the current page has an [`active`](../serviceworkerregistration/active) worker. Once that condition is met, it resolves with the [`ServiceWorkerRegistration`](../serviceworkerregistration).

Syntax
------

    navigator.serviceWorker.ready.then(function(serviceWorkerRegistration) { ... });

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will never reject, and which may eventually resolve with a [`ServiceWorkerRegistration`](../serviceworkerregistration).

Example
-------

    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.ready
      .then(function(registration) {
        console.log('A service worker is active:', registration.active);

        // At this point, you can call methods that require an active
        // service worker, like registration.pushManager.subscribe()
      });
    } else {
      console.log('Service workers are not supported.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigator-service-worker-ready">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.ready' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ready`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/ready" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/ready</a>
