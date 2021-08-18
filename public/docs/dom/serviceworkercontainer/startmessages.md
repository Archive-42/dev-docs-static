ServiceWorkerContainer.startMessages()
======================================

The `startMessages()` method of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface explicitly starts the flow of messages being dispatched from a service worker to pages under its control (e.g. sent via [`Client.postMessage()`](../client/postmessage)). This can be used to react to sent messages earlier, even before that page's content has finished loading.

Explanation
-----------

By default, all messages sent from a page's controlling service worker to the page (using [`Client.postMessage()`](../client/postmessage)) are queued while the page is loading, and get dispatched once the page's HTML document has been loaded and parsed (i.e. after the `DOMContentLoaded` event fires). It's possible to start dispatching these messages earlier by calling [`ServiceWorkerContainer.startMessages()`](startmessages), for example if you've invoked a message handler using [`EventTarget.addEventListener()`](../eventtarget/addeventlistener) before the page has finished loading, but want to start processing the messages right away.

**Note**: The messages start being sent automatically when setting the handler directly using [`ServiceWorkerContainer.onmessage`](onmessage). In this you don't need `startMessages()`.

Syntax
------

    serviceWorkerContainer.startMessages();

### Parameters

None.

### Return value

`undefined`.

Examples
--------

    if('serviceWorker' in navigator) {
      navigator.serviceWorker
               .register('/sw.js')
               .then(function() { console.log('Service Worker Registered'); });
    }

    // ...

    navigator.serviceWorker.addEventListener('message', (e) => {
      // ...
    });

    navigator.serviceWorker.startMessages();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkercontainer-startmessages">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerContainer: startMessages()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`startMessages`

74

≤79

64

No

62

Yes

74

74

64

50

Yes

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/startMessages" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/startMessages</a>
