# PresentationConnection.send()

The `send()` method of the [`PresentationConnection`](../presentationconnection) interface tells a controlling browsing context to send binary or text data to a presenting browsing context.

## Syntax

    PresentationConnection.send(data);

### Parameters

`data`  
The data to send to the presentation context. It will be one of the following:

- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [`Blob`](../blob)
- [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

### Return value

`undefined`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#dom-presentationconnection-send">Presentation API<br />
<span class="small">The definition of 'send()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`send`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/send" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/send</a>
