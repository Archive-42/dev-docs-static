# RTCDTMFToneChangeEvent.tone

The read-only property `RTCDTMFToneChangeEvent.tone` returns the DTMF character which has just begun to play, or an empty string (`""`). if all queued tones have finished playing (that is, [`RTCDTMFSender.toneBuffer`](../rtcdtmfsender/tonebuffer) is empty).

## Syntax

     var tone = dtmfToneChangeEvent.tone;

## Example

This example establishes a handler for the `tonechange` event which updates an element to display the currently playing tone in its content, or, if all tones have played, the string "&lt;none&gt;".

    dtmfSender.ontonechange = function( ev ) {
      let tone = ev.tone;
      if (tone === "") {
        tone = "&lt;none&gt;"
      }

      document.getElementById("playingTone").innerText = tone;
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtmftonechangeevent-tone">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFToneChangeEvent.tone' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`tone`

27

12

52

No

Yes

13.1

4.4

27

52

Yes

13.4

1.5

## See also

- [WebRTC](../webrtc_api)
- [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
- `toneevent`
- [`RTCDTMFToneChangeEvent`](../rtcdtmftonechangeevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/tone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent/tone</a>
