# RTCDTMFSender.toneBuffer

The [`RTCDTMFSender`](../rtcdtmfsender) interface's toneBuffer property returns a string containing a list of the [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones currently queued for sending to the remote peer over the [`RTCPeerConnection`](../rtcpeerconnection). To place tones into the buffer, call [`insertDTMF()`](insertdtmf).

Tones are removed from the string as they're played, so only upcoming tones are listed.

## Syntax

    var toneBuffer = RTCDTMFSender.toneBuffer;

### Value

A [`DOMString`](../domstring) listing the tones to be played. If the string is empty, there are no tones pending.

### Tone buffer format

The tone buffer is a string which can contain any combination of the characters that are permitted by the DTMF standard.

#### DTMF tone characters

The digits 0-9  
These characters represent the digit keys on a telephone keypad.

The letters A-D  
These characters represent the "A" through "D" keys which are part of the DTMF standard but not included on most telephones. These are _not_ interpreted as digits. Lower-case "a"-"d" automatically gets converted to upper-case.

The pound/hash sign ("\#") and the asterisk ("\*")  
These correspond to the similarly-labeled keys which are typically on the bottom row of the telephone keypad.

The comma (",")  
This character instructs the dialing process to pause for two seconds before sending the next character in the buffer.

All other characters are unrecognized and will cause [`insertDTMF()`](insertdtmf) to throw an `InvalidCharacterError` exception.

#### Using tone buffer strings

For example, if you're writing code to control a voicemail system by sending DTMF codes, you might use a string such as "\*,1,5555". In this example, we would send "\*" to request access to the VM system, then, after a pause, send a "1" to start playback of voicemail messages, then after a pause, dial "5555" as a PIN number to open the messages.

Settting the tone buffer to an empty string (`""`) cancels any pending DTMF codes.

## Example

tbd

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-RTCDTMFSender-tonebuffer">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFSender.toneBuffer' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`toneBuffer`

27

≤79

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

- [WebRTC API](../webrtc_api)
- [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
- [`RTCDTMFSender.insertDTMF()`](insertdtmf)
- [`RTCPeerConnection`](../rtcpeerconnection)
- [`RTCDTMFSender`](../rtcdtmfsender)
- [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/toneBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/toneBuffer</a>
