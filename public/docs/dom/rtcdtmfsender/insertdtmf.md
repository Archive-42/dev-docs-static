RTCDTMFSender.insertDTMF()
==========================

The `insertDTMF``()` method on the [`RTCDTMFSender`](../rtcdtmfsender) interface starts sending [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tones to the remote peer over the [`RTCPeerConnection`](../rtcpeerconnection). Sending of the tones is performed asynchronously, with `tonechange` events sent to the `RTCDTMFSender` every time a tone starts or ends.

As long as the connection is active, you can send tones at any time. Calling `insertDTMF()` will append the specified tones to the end of the current tone buffer, so that those tones play after the previously-enqueued tones.

Syntax
------

    RTCDTMFSender.insertDTMF(tones[, duration[, interToneGap]]);

### Parameters

`tones`  
A [`DOMString`](../domstring) containing the DTMF codes to be transmitted to the recipient. Specifying an empty string as the `tones` parameter clears the tone buffer, aborting any currently queued tones. A "," character inserts a two second delay.

 `duration` <span class="badge inline optional">Optional</span>   
The amount of time, in milliseconds, that each DTMF tone should last. This value must be between 40 ms and 6000 ms (6 seconds), inclusive. The default is 100 ms.

 `interToneGap` <span class="badge inline optional">Optional</span>   
The length of time, in milliseconds, to wait between tones. The browser will enforce a minimum value of 30 ms (that is, if you specify a lower value, 30 ms will be used instead); the default is 70 ms.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

`InvalidStateError`  
The DTMF tones couldn't be sent because the track has been stopped, or is in a read-only or inactive state.

`InvalidCharacterError`  
One or more of the characters in `tones` is not valid DTMF.

Example
-------

tbd

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-RTCDTMFSender-insertDTMF">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDTMFSender.insertDTMF()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Using DTMF with WebRTC](../webrtc_api/using_dtmf)
-   [`RTCPeerConnection`](../rtcpeerconnection)
-   [`RTCDTMFSender`](../rtcdtmfsender)
-   [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/insertDTMF" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDTMFSender/insertDTMF</a>
