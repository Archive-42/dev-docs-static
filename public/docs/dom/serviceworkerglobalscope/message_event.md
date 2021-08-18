ServiceWorkerGlobalScope: message event
=======================================

The `message` event of the [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) interface occurs when incoming messages are received. Controlled pages can use the <span class="page-not-created">`ServiceWorker.postMessage()`</span> method to send messages to service workers.  
The service worker can optionally send a response back via the [`Client.postMessage()`](../client/postmessage), corresponding to the controlled page.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../extendablemessageevent"><code>ExtendableMessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

Examples
--------

In the below example a page gets a handle to the [`ServiceWorker`](../serviceworker) object via [`ServiceWorkerRegistration.active`](../serviceworkerregistration/active), and then calls its `postMessage()` function.

    // in the page being controlled
    if (navigator.serviceWorker) {

      navigator.serviceWorker.register('service-worker.js');

      navigator.serviceWorker.addEventListener('message', event => {
        // event is a MessageEvent object
        console.log(`The service worker sent me a message: ${event.data}`);
      });

      navigator.serviceWorker.ready.then( registration => {
        registration.active.postMessage("Hi service worker");
      });

    }

The service worker can receive the message by listening to the `message` event:

    // in the service worker
    addEventListener('message', event => {
      // event is an ExtendableMessageEvent object
      console.log(`The client sent me a message: ${event.data}`);

      event.source.postMessage("Hi client");
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#eventdef-serviceworkerglobalscope-message">Service Workers<br />
<span class="small">The definition of 'message' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`message_event`

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
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerGlobalScope/message_event</a>
