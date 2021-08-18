# MessagePort.onmessageerror

The `onmessageerror` event handler of the [`MessagePort`](../messageport) interface is an [`EventListener`](../eventlistener), called whenever an [`MessageEvent`](../messageevent) of type `messageerror` is fired on the port—that is, when it receives a message that cannot be [deserialized](https://developer.mozilla.org/en-US/docs/Glossary/Deserialization).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    port.onmessageerror = function() { ... };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#handler-messageport-onmessageerror">HTML Living Standard<br />
<span class="small">The definition of 'onmessageerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onmessageerror`

60

18

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

## See also

- [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/onmessageerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/onmessageerror</a>
