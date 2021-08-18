# MessageEvent.lastEventId

The `lastEventId` read-only property of the [`MessageEvent`](../messageevent) interface is a [`DOMString`](../domstring) representing a unique ID for the event.

## Syntax

    var myId = messageEvent.lastEventId;

### Value

A [`DOMString`](../domstring) representing the ID.

## Example

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
      console.log(e.lastEventId);
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-messageevent-lasteventid">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent: lastEventId' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lastEventId`

1

17

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

## See also

- [`ExtendableMessageEvent`](../extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/lastEventId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/lastEventId</a>
