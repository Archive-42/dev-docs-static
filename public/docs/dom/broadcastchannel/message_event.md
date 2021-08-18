# BroadcastChannel: message event

The `message` event is fired on a [`BroadcastChannel`](../broadcastchannel) object when a message arrives on that channel.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessage</code></td></tr></tbody></table>

## Examples

### Live example

In this example there's a "sender" `<iframe>` that broadcasts the contents of a `<textarea>` when the user clicks a button. There are two "receiver" iframes that listen to the broadcast message and write the result into a `<div>` element.

#### Sender

    const channel = new BroadcastChannel('example-channel');
    const messageControl = document.querySelector('#message');
    const broadcastMessageButton = document.querySelector('#broadcast-message');

    broadcastMessageButton.addEventListener('click', () => {
        channel.postMessage(messageControl.value);
    })

#### Receiver 1

    const channel = new BroadcastChannel('example-channel');
    channel.addEventListener('message', (event) => {
      received.textContent = event.data;
    });

#### Receiver 2

    const channel = new BroadcastChannel('example-channel');
    channel.addEventListener('message', (event) => {
      received.textContent = event.data;
    });

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-message">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

## Browser compatibility

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

54

≤79

38

No

41

No

54

54

38

41

No

6.0

## See also

- Related events: `messageerror`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/message_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/message_event</a>
