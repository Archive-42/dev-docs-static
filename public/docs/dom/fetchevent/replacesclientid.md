FetchEvent.replacesClientId
===========================

The `replacesClientId` read-only property of the [`FetchEvent`](../fetchevent) interface is the [`id`](../client/id) of the [`client`](../client) that is being replaced during a page navigation.

For example, when navigating from page A to page B `replacesClientId` is the ID of the client associated with page A. It can be an empty string when navigating from `about:blank` to another page, as `about:blank`'s client will be reused, rather than be replaced.

Additionally, if the fetch isn't a navigation, `replacesClientId` will be an empty string. This could be used to access/communicate with a client that will imminently be replaced, right before a navigation.

Syntax
------

    var myReplacedClientId = fetchEvent.replacesClientId;

### Value

A [`DOMString`](../domstring).

Example
-------

    self.addEventListener('fetch', function(event) {
      console.log(event.replacesClientId);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-replacesclientid">Service Workers<br />
<span class="small">The definition of 'replacesClientId' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`replacesClientId`

No

18-79

65

No

No

No

No

No

65

No

No

No

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/replacesClientId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/replacesClientId</a>
