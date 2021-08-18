FetchEvent.resultingClientId
============================

The `resultingClientId` read-only property of the [`FetchEvent`](../fetchevent) interface is the [`id`](../client/id) of the [`client`](../client) that replaces the previous client during a page navigation.

For example, when navigating from page A to page B `resultingClientId` is the ID of the client associated with page B.

If the fetch request is a subresource request or the request's `destination` is `report`, `resultingClientId` will be an empty string.

Syntax
------

    var myResultingClientId = fetchEvent.resultingClientId;

### Value

A [`DOMString`](../domstring).

Example
-------

    self.addEventListener('fetch', function(event) {
      console.log(event.resultingClientId);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-resultingclientid">Service Workers<br />
<span class="small">The definition of 'resultingClientId' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resultingClientId`

72

18

65

No

60

No

72

72

65

50

No

11.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/resultingClientId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/resultingClientId</a>
