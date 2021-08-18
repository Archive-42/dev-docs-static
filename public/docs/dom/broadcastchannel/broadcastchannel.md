# BroadcastChannel()

The `BroadcastChannel()` constructor creates a new [`BroadcastChannel`](../broadcastchannel) and connects it to the underlying channel.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

     channel = new BroadcastChannel(channel);

### Values

_channel_  
Is a [`DOMString`](../domstring) representing the name of the channel; there is one single channel with this name for all [browsing contexts](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) with the same [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin).

## Example

    // create a new channel listening to the "internal_notification" channel.

    var bc = new BroadcastChannel('internal_notification');
    bc.postMessage('New listening connected!');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-broadcastchannel">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BroadcastChannel`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/BroadcastChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/BroadcastChannel</a>
