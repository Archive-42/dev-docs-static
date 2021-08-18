ServiceWorkerContainer.oncontrollerchange
=========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `oncontrollerchange` property of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface is an event handler fired whenever a `controllerchange` event occurs — when the document's associated [`ServiceWorkerRegistration`](../serviceworkerregistration) acquires a new [`active`](../serviceworkerregistration/active) worker.

Syntax
------

    serviceWorkerContainer.oncontrollerchange = function(controllerchangeevent) { ... }

Example
-------

    // TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkercontainer-oncontrollerchange">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerContainer: oncontrollerchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`oncontrollerchange`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/oncontrollerchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/oncontrollerchange</a>
