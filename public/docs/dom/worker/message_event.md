Worker: message event
=====================

The `message` event is fired on a [`Worker`](../worker) object when the worker's parent receives a message from its worker (i.e. when the worker sends a message using `DedicatedWorkerGlobalScope.postMessage()`).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

Examples
--------

This code creates a new worker and listens to messages from it using `addEventListener()`:

    const worker = new Worker("static/scripts/worker.js");

    worker.addEventListener('message', (event) => {
        console.log(`Received message from worker: ${event.data}`)
    });

Alternatively, it could listen using the `onmessage` event handler property:

    const worker = new Worker("static/scripts/worker.js");

    worker.onmessage = (event) => {
        console.log(`Received message from worker: ${event.data}`)
    };

The worker posts messages using `self.postMessage()`:

    // static/scripts/worker.js

    self.postMessage('I\'m alive!');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-message">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

4

12

3.5

10

10.6

4

4

18

4

11.5

5.1

1.0

See also
--------

-   Related events: `messageerror`.
-   `DedicatedWorkerGlobalScope.postMessage()`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker/message_event</a>
