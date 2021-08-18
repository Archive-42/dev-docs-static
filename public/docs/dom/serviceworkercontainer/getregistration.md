ServiceWorkerContainer.getRegistration()
========================================

The `getRegistration()` method of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface gets a [`ServiceWorkerRegistration`](../serviceworkerregistration) object whose scope URL matches the provided document URL. The method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`ServiceWorkerRegistration`](../serviceworkerregistration) or `undefined`.

Syntax
------

    serviceWorkerContainer.getRegistration(scope).then(function(serviceWorkerRegistration) { ... });

### Parameters

 `scope` <span class="badge inline optional">Optional</span>   
A unique identifier for a service worker registration — the scope URL of the registration object you want to return. This is usually a relative URL.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`ServiceWorkerRegistration`](../serviceworkerregistration) object or `undefined`.

Example
-------

    navigator.serviceWorker.getRegistration('/app').then(function(registration) {
      if(registration){
        document.querySelector('#status').textContent = 'ServiceWorkerRegistration found.';
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkercontainer-getregistration">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerContainer: getRegistration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getRegistration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/getRegistration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/getRegistration</a>
