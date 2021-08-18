Window: message event
=====================

The `message` event is fired on a [`Window`](../window) object when the window receives a message, for example from a call to `Window.postMessage()` from another browsing context.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

Examples
--------

Suppose a script sends a message to a different browsing context, such as another `<iframe>`, using code like this:

    const targetFrame = window.top.frames[1];
    const targetOrigin = 'https://example.org';
    const windowMessageButton = document.querySelector('#window-message');

    windowMessageButton.addEventListener('click', () => {
        targetFrame.postMessage('hello there', targetOrigin);
    });

The receiver can listen for the message using `addEventListener()` with code like this:

    window.addEventListener('message', (event) => {
        console.log(`Received message: ${event.data}`);
    });

Alternatively the listener could use the `onmessage` event handler property:

    window.onmessage = (event) => {
        console.log(`Received message: ${event.data}`);
    };

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

60

≤79

?

?

47

?

60

60

?

47

?

8.0

See also
--------

-   Related events: `messageerror`.
-   `Window.postMessage()`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event</a>
