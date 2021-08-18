ServiceWorkerContainer: message event
=====================================

The `message` event is used in a page controlled by a service worker to receive messages from the service worker.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

Examples
--------

In this example the service worker get the client's ID from a [`fetch`](../serviceworkerglobalscope/onfetch) event and then sends it a message using [`Client.postMessage`](../client/postmessage):

    // in the service worker
    async function messageClient(clientId) {
        const client = await clients.get(clientId);
        client.postMessage('Hi client!');
    }

    addEventListener('fetch', (event) => {
        messageClient(event.clientId);
        event.respondWith(() => {
          // ...
        });
    });

The client can receive the message by listening to the `message` event:

    // in the page being controlled
    navigator.serviceWorker.addEventListener('message', (message) => {
        console.log(message);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkercontainer-onmessage">Service Workers<br />
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

-   [Using Service Workers](../service_worker_api/using_service_workers)
-   [Service workers basic code example](https://github.com/mdn/sw-test)
-   [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
-   [Using web workers](../web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/message_event</a>
