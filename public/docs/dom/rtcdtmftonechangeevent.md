# RTCDTMFToneChangeEvent

The `RTCDTMFToneChangeEvent` interface represents events sent to indicate that [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones have started or finished playing. This interface is used by the `tonechange` event.

## Properties

_In addition to the properties of [`Event`](event), this interface offers the following:_

[`RTCDTMFToneChangeEvent.tone`](rtcdtmftonechangeevent/tone) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the tone which has begun playing, or an empty string (`""`) if the previous tone has finished playing.

## Constructors

[`RTCDTMFToneChangeEvent()`](rtcdtmftonechangeevent/rtcdtmftonechangeevent)  
Returns a new `RTCDTMFToneChangeEvent`. It takes two parameters, the first being a [`DOMString`](domstring) representing the type of the event (always `"tonechange"`); the second a dictionary containing the initial state of the properties of the event.

## Methods

_Supports the methods defined in [`Event`](event). There are no additional methods._

## Examples

This snippet is derived loosely from the full, working example you'll find in [When a tone finishes playing](webrtc_api/using_dtmf#when_a_tone_finishes_playing) in [Using DTMF with WebRTC](webrtc_api/using_dtmf). It appends each tone to a display box as it's played, and, once all tones have been sent, re-enabled a previously-disabled "Send" button, allowing the next DMTF string to be entered.

    dtmfSender.addEventListener("change", function(event) {
      if (event.tone !== "") {
        dialStringBox.innerText += event.tone;
      } else {
        sendDTMFButton.disabled = false;
      }
    }, false);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-RTCDTMFSender-tonechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFToneChangeEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCDTMFToneChangeEvent`

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

`RTCDTMFToneChangeEvent`

27

≤18

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

- [WebRTC](webrtc_api)
- Its usual target: [`RTCDTMFSender`](rtcdtmfsender).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFToneChangeEvent</a>
