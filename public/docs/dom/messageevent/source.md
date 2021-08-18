# MessageEvent.source

The `source` read-only property of the [`MessageEvent`](../messageevent) interface is a `MessageEventSource` (which can be a <span class="page-not-created">`WindowProxy`</span>, [`MessagePort`](../messageport), or [`ServiceWorker`](../serviceworker) object) representing the message emitter.

## Syntax

    let mySource = messageEvent.source;

### Value

a `MessageEventSource` (which can be a <span class="page-not-created">`WindowProxy`</span>, [`MessagePort`](../messageport), or [`ServiceWorker`](../serviceworker) object) representing the message emitter.

## Example

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
      console.log(e.source);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-messageevent-source">HTML Living Standard<br />
<span class="small">The definition of ' MessageEvent: source' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`source`

Yes

12

55

No

Yes

Yes

Yes

Yes

55

Yes

Yes

Yes

`MessageEventSource_type`

Yes

≤79

55

No

?

?

Yes

Yes

55

?

?

Yes

## See also

- [`ExtendableMessageEvent`](../extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/source" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/source</a>
