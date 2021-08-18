# BroadcastChannel.postMessage()

The `BroadcastChannel.postMessage()` sends a message, which can be of any kind of [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), to each listener in any [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) with the same [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin). The message is transmitted as a `message` event targeted at each `BroadcastChannel` bound to the channel.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var str = channel.postMessage(object);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-broadcastchannel-postmessage">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel.postmessage()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`postMessage`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/postMessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/postMessage</a>
