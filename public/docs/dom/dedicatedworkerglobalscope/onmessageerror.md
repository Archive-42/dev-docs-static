# DedicatedWorkerGlobalScope.onmessageerror

The `onmessageerror` event handler of the [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) interface is an [`EventListener`](../eventlistener), called whenever an [`MessageEvent`](../messageevent) of type `messageerror` is fired on the worker—that is, when it receives a message that cannot be [deserialized](https://developer.mozilla.org/en-US/docs/Glossary/Deserialization).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    onmessageerror = function() { ... };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-dedicatedworkerglobalscope-onmessageerror">HTML Living Standard<br />
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

?

47

?

60

60

57

44

?

8.0

## See also

- [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/onmessageerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope/onmessageerror</a>
