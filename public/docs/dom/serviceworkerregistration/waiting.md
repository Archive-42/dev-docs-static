ServiceWorkerRegistration.waiting
=================================

The `waiting` property of the [`ServiceWorkerRegistration`](../serviceworkerregistration) interface returns a service worker whose [`ServiceWorker.state`](../serviceworker/state) is `installed`. This property is initially set to `null`.

**Note**: This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var serviceWorker = serviceWorkerRegistration.waiting;

### Value

A [`ServiceWorker`](../serviceworker) object, if it is currently in an `installed` state.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigator-service-worker-waiting">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.waiting' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.<br />
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

`waiting`

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

No

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/waiting" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerRegistration/waiting</a>
