Navigator.serviceWorker
=======================

The `Navigator.serviceWorker` read-only property returns the [`ServiceWorkerContainer`](../serviceworkercontainer) object for the [associated document](https://html.spec.whatwg.org/multipage/browsers.html#concept-document-window), which provides access to registration, removal, upgrade, and communication with the [`ServiceWorker`](../serviceworker).

The feature may not be available in private mode.

Syntax
------

    const workerContainerInstance = navigator.serviceWorker;

### Value

[`ServiceWorkerContainer`](../serviceworkercontainer).

Examples
--------

This code checks if the browser supports service workers.

    if ('serviceWorker' in navigator) {
      // Supported!
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#navigator-serviceworker">Service Workers<br />
<span class="small">The definition of 'navigator.serviceWorker' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`serviceWorker`

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

-   [Service Worker API](../service_worker_api)
-   [Using Service Workers](../service_worker_api/using_service_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/serviceWorker</a>
