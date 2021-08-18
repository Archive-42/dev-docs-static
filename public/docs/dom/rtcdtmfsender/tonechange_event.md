# RTCDTMFSender: tonechange event

The `tonechange` event is sent to an [`RTCDTMFSender`](../rtcdtmfsender) by the [WebRTC API](../webrtc_api) to indicate when [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones previously queued for sending (by calling [`RTCDTMFSender.insertDTMF()`](insertdtmf)) begin and end.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcdtmftonechangeevent"><code>RTCDTMFToneChangeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ontonechange"><code>ontonechange</code></a></td></tr></tbody></table>

To determine what tone started playing, or if a tone stopped playing, check the value of the event's [`tone`](../rtcdtmftonechangeevent/tone) property.

## Examples

This example establishes a handler for the `tonechange` event which updates an element to display the currently playing tone in its content, or, if all tones have played, the string "&lt;none&gt;".

This can be done using [`addEventListener()`](../eventtarget/addeventlistener):

    dtmfSender.addEventListener("tonechange", ev => {
      let tone = ev.tone;
      if (tone === "") {
        tone = "&lt;none&gt;";
      }

      document.getElementById("playingTone").innerText = tone;
    }, false);

You can also just set the [`ontonechange`](ontonechange) event handler property directly:

    dtmfSender.ontonechange = function( ev ) {
      let tone = ev.tone;
      if (tone === "") {
        tone = "&lt;none&gt;"
      }

      document.getElementById("playingTone").innerText = tone;
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-RTCDTMFSender-tonechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'tonechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Definition for the WebRTC API</td></tr></tbody></table>

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

`tonechange_event`

27

≤79

52

No

Yes

?

Yes

27

52

Yes

?

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/tonechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/tonechange_event</a>
