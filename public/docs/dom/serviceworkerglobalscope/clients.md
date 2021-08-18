ServiceWorkerGlobalScope.clients
================================

The `clients` read-only property of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface returns the [`Clients`](../clients) object associated with the service worker.

Syntax
------

    swClients = self.clients

### Value

The [`Clients`](../clients) object associated with the specific worker.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-global-scope-clients">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerRegistration.clients' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.<br />
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

`clients`

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
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/clients" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/clients</a>
