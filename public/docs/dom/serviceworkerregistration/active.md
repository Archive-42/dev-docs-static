ServiceWorkerRegistration.active
================================

The `active` property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a service worker whose [`ServiceWorker.state`](../serviceworker/state) is `activating` or `activated`. This property is initially set to `null`.

An active worker controls a [`Client`](../client) if the client's URL falls within the scope of the registration (the `scope` option set when [`ServiceWorkerContainer.register`](../serviceworkercontainer/register) is first called.)

**Note**: This feature is available in [Web Workers](../web_workers_api).

**Note**: Once an active worker is `activating`, neither a runtime script error nor a force termination of the active worker prevents the active worker from getting `activated`.

Syntax
------

    var serviceWorker = serviceWorkerRegistration.active;

### Value

A [`ServiceWorker`](../serviceworker) object's property, if it is currently in an `activating` or `activated` state.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkerregistration-active">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.active' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.<br />
</td></tr></tbody></table>

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

`active`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/active" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/active</a>
