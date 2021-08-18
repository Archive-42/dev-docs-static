MessagePort: message event
==========================

The `message` event is fired on a [`MessagePort`](../messageport) object when a message arrives on that channel.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

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

The target can receive the port and start listening for messages on it using code like this:

    window.addEventListener('message', (event) => {
        const myPort = event.ports[0];

        myPort.addEventListener('message', (event) => {
            received.textContent = event.data;
        });

        myPort.start();
    });

Note that the listener must call `MessagePort.start()` before any messages will be delivered to this port. This is only needed when using the `addEventListener()` method: if the receiver uses `onmessage` instead, `start()` is called implicitly:

    window.addEventListener('message', (event) => {
        const myPort = event.ports[0];

        myPort.onmessage = (event) => {
            received.textContent = event.data;
        };
    });

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

Yes

10

10.6

5

≤37

18

No

11.5

5.1

1.0

See also
--------

-   Related events: `messageerror`.
-   [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/message_event</a>
