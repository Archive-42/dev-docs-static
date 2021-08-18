# BroadcastChannel.name

The read-only `BroadcastChannel.name` property returns a [`DOMString`](../domstring), which uniquely identifies the given channel with its name. This name is passed to the [`BroadcastChannel()`](broadcastchannel) constructor at creation time and is therefore read-only.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var str = channel.name;

## Examples

    // Connect to a channel
    var bc = new BroadcastChannel('test_channel');

    // More operations (like postMessage, …)

    // Log the channel name to the console
    console.log(bc.name); // "test_channel"

    // When done, disconnect from the channel
    bc.close();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#dom-broadcastchannel-name">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel.name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/name</a>
