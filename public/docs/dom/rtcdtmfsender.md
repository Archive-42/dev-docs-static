RTCDTMFSender
=============

The `RTCDTMFSender` interface provides a mechanism for transmitting [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) codes on a [WebRTC](webrtc_api) [`RTCPeerConnection`](rtcpeerconnection). You gain access to the connection's `RTCDTMFSender` through the [`RTCRtpSender.dtmf`](rtcrtpsender/dtmf) property on the audio track you wish to send DTMF with.

The primary purpose for WebRTC's DTMF support is to allow WebRTC-based communication clients to be connected to a [public-switched telephone network](https://en.wikipedia.org/wiki/Public-switched_telephone_network) (PSTN) or other legacy telephone service, including extant voice over IP (VoIP) services. For that reason, DTMF can't be used between two WebRTC-based devices, because there is no mechanism provided by WebRTC for receiving DTMF codes.

Properties
----------

 [`RTCDTMFSender.toneBuffer`](rtcdtmfsender/tonebuffer) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) which contains the list of DTMF tones currently in the queue to be transmitted (tones which have already been played are no longer included in the string). See [`toneBuffer`](rtcdtmfsender/tonebuffer) for details on the format of the tone buffer.

Methods
-------

[`RTCDTMFSender.insertDTMF()`](rtcdtmfsender/insertdtmf)  
Given a string describing a set of DTMF codes and, optionally, the duration of and inter-tone gap between the tones, `insertDTMF()` starts sending the specified tones. Calling `insertDTMF()` replaces any already-pending tones from the `toneBuffer`. You can abort sending queued tones by specifying an empty string (`""`) as the set of tones to play.

Events
------

Listen to these events using [`addEventListener()`](eventtarget/addeventlistener) or by assigning an event listener to the `oneventname` property of this interface.

[`tonechange`](rtcdtmfsender/tonechange_event)  
The `tonechange` event is sent to the `RTCDTMFSender` instance's event handler to indicate that a tone has either started or stopped playing.  
Also available using the [`ontonechange`](rtcdtmfsender/ontonechange) event handler property.

Example
-------

See the article [Using DTMF with WebRTC](webrtc_api/using_dtmf) for a full example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcdtmfsender">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFSender' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`RTCDTMFSender`

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

`canInsertDTMF`

27

≤79

No

No

Yes

13.1

≤37

27

No

Yes

13.4

1.5

`insertDTMF`

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

`ontonechange`

27

≤79

52

No

Yes

13.1

≤37

27

52

Yes

13.4

1.5

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

See also
--------

-   [WebRTC API](webrtc_api)
-   [Using DTMF with WebRTC](webrtc_api/using_dtmf)
-   [`RTCRtpSender.dtmf`](rtcrtpsender/dtmf)
-   [`RTCPeerConnection`](rtcpeerconnection)
-   [`RTCRtpSender`](rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender</a>
