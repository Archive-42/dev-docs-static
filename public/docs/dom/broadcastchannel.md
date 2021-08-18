# BroadcastChannel

The `BroadcastChannel` interface represents a named channel that any [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) of a given [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) can subscribe to. It allows communication between different documents (in different windows, tabs, frames or iframes) of the same origin. Messages are broadcasted via a `message` event fired at all `BroadcastChannel` objects listening to the channel.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Constructor

[`BroadcastChannel()`](broadcastchannel/broadcastchannel)  
Creates an object linking to the named channel.

## Properties

_This interface also inherits properties from its parent, [`EventTarget`](eventtarget)._

[`BroadcastChannel.name`](broadcastchannel/name) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring), the name of the channel.

### Event handlers

[`BroadcastChannel.onmessage`](broadcastchannel/onmessage)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) property that specifies the function to execute when a `message` event is fired on this object.

[`BroadcastChannel.onmessageerror`](broadcastchannel/onmessageerror)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when a [`MessageEvent`](messageevent) of type <span class="page-not-created">`MessageError`</span> is fired—that is, when it receives a message that cannot be deserialized.

## Methods

_This interface also inherits methods from its parent, [`EventTarget`](eventtarget)._

[`BroadcastChannel.postMessage()`](broadcastchannel/postmessage)  
Sends the message, of any type of object, to each `BroadcastChannel` object listening to the same channel.

[`BroadcastChannel.close()`](broadcastchannel/close)  
Closes the channel object, indicating it won't get any new messages, and allowing it to be, eventually, garbage collected.

## Events

`message`  
Fired when a message arrives on the channel.  
Also available via the `onmessage` property.

`messageerror`  
Fired when a message arrives that can't be deserialized.  
Also available via the `onmessageerror` property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/comms.html#broadcastchannel">HTML Living Standard<br />
<span class="small">The definition of 'BroadcastChannel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onmessageerror`

60

79

57

No

47

No

60

60

57

44

No

8.0

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

- Another, more heavyweight, way of communicating between browser contexts: [`ServiceWorker`](serviceworker).
- [Broadcast Channel API overview](broadcast_channel_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel</a>
