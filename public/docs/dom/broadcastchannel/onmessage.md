# BroadcastChannel.onmessage

The `BroadcastChannel.onmessage` event handler is a property that specifies the function to execute when a `message` event, of type [`MessageEvent`](../messageevent), is received by this [`BroadcastChannel`](../broadcastchannel). Such an event is sent by the browser with a message broadcasted to the channel.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    channel.onmessage = function;

### Values

- `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type [`MessageEvent`](../messageevent).

## Example

    bc.onmessage = function(ev) { console.log(`message event received! '${ev.data}'`); };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#handler-broadcastchannel-onmessage">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel.onmessage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onmessage`

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

- Another, more heavy weight, way of communicating between browser contexts: [`ServiceWorker`](../serviceworker)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/onmessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel/onmessage</a>
