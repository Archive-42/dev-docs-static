ServiceWorkerContainer.controller
=================================

The `controller` read-only property of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface returns a [`ServiceWorker`](../serviceworker) object if its state is `activating` or `activated` (the same object returned by [`ServiceWorkerRegistration.active`](../serviceworkerregistration/active)). This property returns `null` if the request is a force refresh (*Shift* + refresh) or if there is no active worker.

Syntax
------

    var myController = navigator.serviceWorker.controller;

### Value

A [`ServiceWorker`](../serviceworker) object.

Example
-------

    if ('serviceWorker' in navigator) {
      // Do a one-off check to see if a service worker's in control.
      if (navigator.serviceWorker.controller) {
        console.log(`This page is currently controlled by: ${navigator.serviceWorker.controller}`);
      } else {
        console.log('This page is not currently controlled by a service worker.');
      }
    } else {
      console.log('Service workers are not supported.');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigator-service-worker-controller">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.controller' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`controller`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/controller" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/controller</a>
