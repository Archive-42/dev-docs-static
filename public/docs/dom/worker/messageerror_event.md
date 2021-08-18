Worker: messageerror event
==========================

The `messageerror` event is fired on a [`Worker`](../worker) object when it receives a message that can't be deserialized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessageerror</code></td></tr></tbody></table>

Examples
--------

Create a worker, and listen for `message` and `messageerror` events using `addEventListener()`:

    // inside main.js

    const worker = new Worker("static/scripts/worker.js");

    worker.addEventListener("message", (event) => {
        console.error(`Received message from worker: ${event}`);
    });

    worker.addEventListener("messageerror", (event) => {
        console.error(`Error receiving message from worker: ${event}`);
    });

The same, but using the `onmessageerror` event handler property:

    // inside main.js

    const worker = new Worker("static/scripts/worker.js");

    worker.onmessage = (event) => {
        console.error(`Received message from worker: ${event}`);
    };

    worker.onmessageerror = (event) => {
        console.error(`Error receiving message from worker: ${event}`);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-messageerror">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`messageerror_event`

60

18

57

?

47

?

60

60

57

47

?

8.0

See also
--------

-   `Worker.postMessage()`
-   Related events: `message`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Worker/messageerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Worker/messageerror_event</a>
