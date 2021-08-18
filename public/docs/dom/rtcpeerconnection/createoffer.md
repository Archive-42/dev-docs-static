RTCPeerConnection.createOffer()
===============================

The `createOffer()` method of the [`RTCPeerConnection`](../rtcpeerconnection) interface initiates the creation of an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) offer for the purpose of starting a new WebRTC connection to a remote peer. The SDP offer includes information about any [`MediaStreamTrack`](../mediastreamtrack)s already attached to the WebRTC session, codec, and options supported by the browser, and any candidates already gathered by the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent, for the purpose of being sent over the signaling channel to a potential peer to request a connection or to update the configuration of an existing connection.

The return value is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which, when the offer has been created, is resolved with a [`RTCSessionDescription`](../rtcsessiondescription) object containing the newly-created offer.

Syntax
------

    aPromise = myPeerConnection.createOffer([options]);

    myPeerConnection.createOffer(successCallback, failureCallback, [options]) 
        This deprecated API should no longer be used, but will probably still work.
        

### Parameters

 `options` <span class="badge inline optional">Optional</span>   
An `RTCOfferOptions` dictionary providing options requested for the offer.

#### RTCOfferOptions dictionary

The `RTCOfferOptions` dictionary is used to customize the offer created by this method.

 `iceRestart` <span class="badge inline optional">Optional</span>   
To restart ICE on an active connection, set this to `true`. This will cause the returned offer to have different credentials than those already in place. If you then apply the returned offer, ICE will restart. Specify `false` to keep the same credentials and therefore not restart ICE. `false`.

 `offerToReceiveAudio` <span class="badge inline optional">Optional</span> (Legacy)  
A legacy Boolean option which used to control whether or not to offer to the remote peer the opportunity to try to send audio. If this value is `false`, the remote peer will not be offered to send audio data, even if the local side will be sending audio data. If this value is `true`, the remote peer will be offered to send audio data, even if the local side will *not* be sending audio data. The default behavior is to offer to receive audio only if the local side is sending audio, not otherwise.

To emulate this behavior in modern implementations, the presence of this member with a value `false`, will set the direction of all existing audio transceivers to exclude reception (i.e. set to either `"sendonly"` or `"inactive"`).

In modern implementations, the presence of this member with a value `true`, will ensure there is at least one transceiver set to receive audio that has not been stopped, and if there isn't one, one will be created.

**Note:** You shouldn't use this legacy property. Instead, use [`RTCRtpTransceiver`](../rtcrtptransceiver) to control whether or not to accept incoming audio.

 `offerToReceiveVideo` <span class="badge inline optional">Optional</span> (Legacy)  
A legacy Boolean option which used to control whether or not to offer to the remote peer the opportunity to try to send video. If this value is `false`, the remote peer will not be offered to send video data, even if the local side will be sending video data. If this value is `true`, the remote peer will be offered to send video data, even if the local side will *not* be sending video data. The default behavior is to offer to receive video only if the local side is sending video, not otherwise.

To emulate this behavior in modern implementations, the presence of this member with a value `false`, will set the direction of all existing video transceivers to exclude reception (i.e. set to either `"sendonly"` or `"inactive"`).

In modern implementations, the presence of this member with a value `true`, will ensure there is at least one transceiver set to receive video that has not been stopped, and if there isn't one, one will be created.

**Note:** You shouldn't use this legacy property. Instead, use [`RTCRtpTransceiver`](../rtcrtptransceiver) to control whether or not to accept incoming video.

 `voiceActivityDetection` <span class="badge inline optional">Optional</span>   
Some codecs and hardware are able to detect when audio begins and ends by watching for "silence" (or relatively low sound levels) to occur. This reduces network bandwidth used for audio by only sending audio data when there's actually something to broadcast. However, in some cases, this is unwanted. For example, in the case of music or other non-voice transmission, this can cause loss of important low-volume sounds. Also, emergency calls should never cut audio when quiet. `true` (voice activity detection *enabled*).

### Deprecated parameters

In older code and documentation, you may see a callback-based version of this function. This has been deprecated and its use is **strongly** discouraged. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `createOffer()` instead. The parameters for this form of `createOffer()` are described below, to aid in updating existing code.

 `successCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`RTCSessionDescriptionCallback`](../rtcsessiondescriptioncallback) which will be passed a single [`RTCSessionDescription`](../rtcsessiondescription) object describing the newly-created offer.

 `errorCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An <span class="page-not-created">`RTCPeerConnectionErrorCallback`</span> which will be passed a single [`DOMException`](../domexception) object explaining why the request to create an offer failed.

 `options` <span class="badge inline optional">Optional</span>   
An optional `RTCOfferOptions` dictionary providing options requested for the offer.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) whose fulfillment handler will receive an object conforming to the <span class="page-not-created">`RTCSessionDescriptionInit`</span> dictionary which contains the SDP describing the generated offer. That received offer should be delivered through the signaling server to a remote peer.

### Exceptions

These exceptions are returned by rejecting the returned promise. Your rejection handler should examine the received exception to determine which occurred.

`InvalidStateError`  
The `RTCPeerConnection` is closed.

`NotReadableError`  
No certificate or set of certificates was provided for securing the connection, and `createOffer()` was unable to create a new one. Since all WebRTC connections are required to be secured, that results in an error.

`OperationError`  
Examining the state of the system to determine resource availability in order to generate the offer failed for some reason.

Example
-------

Here we see a handler for the `negotiationneeded` event which creates the offer and sends it to the remote system over a signaling channel.

**Note:** Keep in mind that this is part of the signaling process, the transport layer for which is an implementation detail that's entirely up to you. In this case, a [WebSocket](../websockets_api) connection is used to send a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) message with a `type` field with the value "video-offer" to the other peer. The contents of the object being passed to the `sendToServer()` function, along with everything else in the promise fulfillment handler, depend entirely on your design.

      myPeerConnection.createOffer().then(function(offer) {
        return myPeerConnection.setLocalDescription(offer);
      })
      .then(function() {
        sendToServer({
          name: myUsername,
          target: targetUsername,
          type: "video-offer",
          sdp: myPeerConnection.localDescription
        });
      })
      .catch(function(reason) {
        // An error occurred, so handle the failure to connect
      });

In this code, the offer is created, and once successful, the local end of the [`RTCPeerConnection`](../rtcpeerconnection) is configured to match by passing the offer (which is represented using an object conforming to <span class="page-not-created">`RTCSessionDescriptionInit`</span>) into [`setLocalDescription()`](setlocaldescription). Once that's done, the offer is sent to the remote system over the signaling channel; in this case, by using a custom function called `sendToServer()`. The implementation of the signaling server is independent from the WebRTC specification, so it doesn't matter how the offer is sent as long as both the caller and potential receiver are using the same one.

Use [`Promise.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) to trap and handle errors.

See [Signaling and video calling](../webrtc_api/signaling_and_video_calling) for the complete example from which this snippet is derived; this will help you to understand how the signaling code here works.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-createoffer">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'createOffer()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createOffer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/createOffer</a>
