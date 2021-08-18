ServiceWorkerMessageEvent.origin
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Important**: In modern browsers, this property has been deprecated. Service worker messages will now use the [`MessageEvent`](../messageevent) interface, for consistency with other web messaging features.

The `origin` read-only property of the [`ServiceWorkerMessageEvent`](../serviceworkermessageevent) interface returns the origin of the service worker's environment settings object.

Syntax
------

    var myOrigin = ServiceWorkerMessageEventInstance.origin;

### Value

A [`DOMString`](../domstring).

Examples
--------

When the following code is used inside the main thread to set up a message channel between it and a service worker for sending messages between the two, the event object of `onmessage` will be a `ServiceWorkerMessageEvent`.

    navigator.serviceWorker.ready.then(function(reg) {

      ...

          // set up a message channel to communicate with the SW
          var channel = new MessageChannel();
          channel.port1.onmessage = function(e) {
            console.log(e.origin);
            handleChannelMessage(e.data);
          }

          mySW = reg.active;
          mySW.postMessage('hello', [channel.port2]);
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

`origin`

45

17

44-55

\["[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.", "In Firefox 55 and later, the standard `MessageEvent` interface must be used instead."\]

No

24

No

No

45

44-55

24

No

4.0

See also
--------

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Channel Messaging](../channel_messaging_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerMessageEvent/origin</a>
