# MediaKeySession.update()

The `MediaKeySession.update()` method loads messages and licenses to the CDM, and then returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) .

## Syntax

    mediaKeySession.update(response).then(function() { ... });

### Parameters

response  
An instance of type BufferSource.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#dom-mediakeysession-update">Encrypted Media Extensions<br />
<span class="small">The definition of 'update()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`update`

42

13

38

No

Yes

12.1

43

42

38

Yes

12.2

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/update" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaKeySession/update</a>
