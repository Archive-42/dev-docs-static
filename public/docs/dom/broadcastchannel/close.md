# BroadcastChannel.close()

The `BroadcastChannel.close()` terminates the connection to the underlying channel, allowing the object to be garbage collected. This is a necessary step to perform as there is no other way for a browser to know that this channel is not needed anymore.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var str = channel.close();

## Example

    // Connect to a channel
    var bc = new BroadcastChannel('test_channel');

    // More operations (like postMessage, …)

    // When done, disconnect from the channel
    bc.close();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-broadcastchannel-close">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel.close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`close`

54

79

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

- [`BroadcastChannel`](../broadcastchannel), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/close</a>
