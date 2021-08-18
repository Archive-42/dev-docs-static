# MediaStream.id

The `MediaStream.id()` read-only property is a [`DOMString`](../domstring) containing 36 characters denoting a unique identifier (GUID) for the object.

## Syntax

    var id = mediaStream.id;

## Example

    var p = navigator.mediaDevices.getUserMedia({ audio: true, video: true });

    p.then(function(stream) {
       console.log(stream.id);
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-id">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream.id' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`id`

Yes-54

12-79

41

No

Yes-39

11

Yes-54

Yes-54

41

Yes-41

11

Yes-6.0

## See also

- [`MediaStream`](../mediastream), the interface this property belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/id</a>
