# MessageEvent.data

The `data` read-only property of the [`MessageEvent`](../messageevent) interface represents the data sent by the message emitter.

## Syntax

    var data = messageEvent.data;

### Value

The data sent by the message emitter; this can be any data type.

## Example

    myWorker.onmessage = function(e) {
      result.textContent = e.data;
      console.log('Message received from worker');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-messageevent-data">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent: data' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`data`

1

12

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/data</a>
