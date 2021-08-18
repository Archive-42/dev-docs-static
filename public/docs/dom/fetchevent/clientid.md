FetchEvent.clientId
===================

The `clientId` read-only property of the [`FetchEvent`](../fetchevent) interface returns the id of the [`Client`](../client) that the current service worker is controlling.

The [`Clients.get()`](../clients/get) method could then be passed this ID to retrieve the associated client.

Syntax
------

    var myClientId = fetchEvent.clientId;

### Value

A [`DOMString`](../domstring) that represents the client ID.

Example
-------

    self.addEventListener('fetch', function(event) {
      console.log(event.clientId);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-clientid">Service Workers<br />
<span class="small">The definition of 'clientId' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clientId`

49

≤79

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

36

No

49

49

45

36

No

5.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/clientId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/clientId</a>
