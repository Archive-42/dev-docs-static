# BroadcastChannel: messageerror event

The `messageerror` event is fired on a [`BroadcastChannel`](../broadcastchannel) object when a message arrives on the channel that can't be deserialized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../messageevent"><code>MessageEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onmessageerror</code></td></tr></tbody></table>

## Examples

This code uses `addEventListener` to listen for messages and errors:

    const channel = new BroadcastChannel('example-channel');

    channel.addEventListener('message', (event) => {
      received.textContent = event.data;
    });

    channel.addEventListener('messageerror', (event) => {
      console.error(event);
    });

The same, but using the `onmessage` and `onmessageerror` event handler properties:

    const channel = new BroadcastChannel('example-channel');

    channel.onmessage = (event) => {
      received.textContent = event.data;
    };

    channel.onmessageerror = (event) => {
      console.log(event);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-messageerror">HTML Living Standard</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`messageerror_event`

60

≤79

57

No

47

No

60

60

57

47

No

8.0

## See also

- Related events: `message`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/messageerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/messageerror_event</a>
