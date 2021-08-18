# MediaStream.getTracks()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **`getTracks()`** method of the [`MediaStream`](../mediastream) interface returns a sequence that represents all the [`MediaStreamTrack`](../mediastreamtrack) objects in this stream's `track set`, regardless of [`MediaStreamTrack.kind`](../mediastreamtrack/kind).

## Syntax

    var mediaStreamTracks = mediaStream.getTracks()

### Parameters

None.

### Return value

An array of [`MediaStreamTrack`](../mediastreamtrack) objects.

## Example

    navigator.mediaDevices.getUserMedia({audio: false, video: true})
    .then(mediaStream => {
      document.querySelector('video').srcObject = mediaStream;
      // Stop the stream after 5 seconds
      setTimeout(() => {
        const tracks = mediaStream.getTracks()
        tracks[0].stop()
      }, 5000)
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-gettracks">Media Capture and Streams<br />
<span class="small">The definition of 'getTracks()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getTracks`

45

12

Yes

No

Yes

11

45

45

Yes

No

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/getTracks</a>
