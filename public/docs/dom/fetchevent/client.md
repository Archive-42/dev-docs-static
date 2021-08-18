FetchEvent.client
=================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `FetchEvent.client` read-only property returns the [`Client`](../client) that the current service worker is controlling.

**Note**: This feature has been deprecated, with its functionality replaced by [`FetchEvent.clientId`](clientid) and [`Clients.get()`](../clients/get). See [this Github issue](https://github.com/slightlyoff/ServiceWorker/issues/723#issuecomment-123516555) for discussion/background.

Syntax
------

    var myClient = FetchEvent.client;

### Value

A [`Client`](../client) object.

Example
-------

    self.addEventListener('fetch', function(event) {
      console.log(event.client);
    });

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

`client`

42

≤79

44

No

27

No

42

44

No

?

No

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/client" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent/client</a>
