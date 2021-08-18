RTCPeerConnection.createAnswer()
================================

The `createAnswer()` method on the [`RTCPeerConnection`](../rtcpeerconnection) interface creates an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) answer to an offer received from a remote peer during the offer/answer negotiation of a WebRTC connection. The answer contains information about any media already attached to the session, codecs and options supported by the browser, and any [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidates already gathered. The answer is delivered to the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), and should then be sent to the source of the offer to continue the negotiation process.

Syntax
------

    aPromise = RTCPeerConnection.createAnswer([options]);

    RTCPeerConnection.createAnswer(successCallback, failureCallback[, options]); 
        This deprecated API should no longer be used, but will probably still work.
        

### Parameters

 `options` <span class="badge inline optional">Optional</span>   
An object which contains options which customize the answer; this is based on the [`RTCAnswerOptions`](../rtcansweroptions) dictionary.

### Deprecated parameters

In older code and documentation, you may see a callback-based version of this function. This has been deprecated and its use is **strongly** discouraged. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `createAnswer()` instead. The parameters for this form of `createAnswer()` are described below, to aid in updating existing code.

 `successCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`RTCSessionDescriptionCallback`](../rtcsessiondescriptioncallback) which will be passed a single [`RTCSessionDescription`](../rtcsessiondescription) object describing the newly-created answer.

 `failureCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An <span class="page-not-created">`RTCPeerConnectionErrorCallback`</span> which will be passed a single [`DOMException`](../domexception) object explaining why the request to create an answer failed.

 `options` <span class="badge inline optional">Optional</span>   
An optional [`RTCOfferOptions`](../rtcofferoptions) object providing options requested for the answer.

### Exceptions

`NotReadableError`  
The identity provider wasn't able to provide an identity assertion.

`OperationError`  
Generation of the SDP failed for some reason; this is a general failure catch-all exception.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) whose fulfillment handler is called with an object conforming to the <span class="page-not-created">`RTCSessionDescriptionInit`</span> dictionary which contains the SDP answer to be delivered to the other peer.

Example
-------

Here is a segment of code taken from the code that goes with the article [Signaling and video calling](../webrtc_api/signaling_and_video_calling). This code comes from the handler for the message sent to carry an offer to another peer across the signaling channel.

Keep in mind that this is part of the signaling process, the transport layer for which is an implementation detail that's entirely up to you. In this case, a [WebSocket](../websockets_api) connection is used to send a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) message with a `type` field with the value "video-answer" to the other peer, carrying the answer to the device which sent the offer to connect. The contents of the object being passed to the `sendToServer()` function, along with everything else in the promise fulfillment handler, depend entirely on your design

    pc.createAnswer().then(function(answer) {
      return pc.setLocalDescription(answer);
    })
    .then(function() {
      // Send the answer to the remote peer through the signaling server.
    })
    .catch(handleGetUserMediaError);

This asks [`RTCPeerConnection`](../rtcpeerconnection) to create and return a new answer. In our promise handler, the returned answer is set as the description of the local end of the connection by calling [`setLocalDescription()`](setlocaldescription).

Once that succeeds, the answer is sent to the signaling server using whatever protocol you see fit.

[`Promise.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) is used to trap and handle errors.

See [Handling the invitation](../webrtc_api/signaling_and_video_calling#handling_the_invitation) in [Signaling and video calling](../webrtc_api/signaling_and_video_calling) to see the complete code, in context, from which this snippet is derived; that will help you understand the signaling process and how answers work.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-createanswer">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'createAnswer()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createAnswer`

51

Promise-based version.

24

15

22

No

43

Promise-based version.

37-43

11

51

Promise-based version.

Yes

51

Promise-based version.

Yes

44

43

Promise-based version.

37-43

11

6.0

Promise-based version and unprefixed.

5.0-6.0

Promise-based version.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createAnswer</a>
