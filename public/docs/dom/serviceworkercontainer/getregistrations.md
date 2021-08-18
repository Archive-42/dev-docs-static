ServiceWorkerContainer.getRegistrations()
=========================================

The `getRegistrations()` method of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface gets all [`ServiceWorkerRegistration`](../serviceworkerregistration)s associated with a `ServiceWorkerContainer`, in an array. The method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`ServiceWorkerRegistration`](../serviceworkerregistration).

Syntax
------

    serviceWorkerContainer.getRegistrations().then(function(serviceWorkerRegistrations) { ... });

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an array of [`ServiceWorkerRegistration`](../serviceworkerregistration) objects.

Example
-------

    navigator.serviceWorker.getRegistrations().then(function(registrations) {
      document.querySelector('#status').textContent = 'ServiceWorkerRegistrations found.';
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigator-service-worker-getRegistrations">Service Workers<br />
<span class="small">The definition of 'getRegistrations()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getRegistrations`

45

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

45

44

27

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/getRegistrations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/getRegistrations</a>
