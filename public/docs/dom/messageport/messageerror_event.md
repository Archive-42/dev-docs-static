MessagePort: messageerror event
===============================

The `messageerror` event is fired on a [`MessagePort`](../messageport) object when it receives a message that can't be deserialized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessageerror</code></td></tr></tbody></table>

Examples
--------

Suppose a script creates a `MessageChannel` and sends one of the ports to a different browsing context, such as another `<iframe>`, using code like this:

    const channel = new MessageChannel();
    const myPort = channel.port1;
    const targetFrame = window.top.frames[1];
    const targetOrigin = 'https://example.org';

    const messageControl = document.querySelector('#message');
    const channelMessageButton = document.querySelector('#channel-message');

    channelMessageButton.addEventListener('click', () => {
        myPort.postMessage(messageControl.value);
    })

    targetFrame.postMessage('init', targetOrigin, [channel.port2]);

The target can receive the port and start listening for messages and message errors on it using code like this:

    window.addEventListener('message', (event) => {
        const myPort = event.ports[0];

        myPort.addEventListener('message', (event) => {
            received.textContent = event.data;
        });

        myPort.addEventListener('messageerror', (event) => {
            console.error(event.data);
        });

        myPort.start();
    });

Note that the listener must call `MessagePort.start()` before any messages will be delivered to this port. This is only needed when using the `addEventListener()` method: if the receiver uses `onmessage` instead, `start()` is called implicitly:

    window.addEventListener('message', (event) => {
        const myPort = event.ports[0];

        myPort.onmessage = (event) => {
            received.textContent = event.data;
        };

        myPort.onmessageerror = (event) => {
            console.error(event.data);
        };

    });

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

-   Related events: `message`.
-   [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/messageerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/messageerror_event</a>
