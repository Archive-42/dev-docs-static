RTCPeerConnection.addIceCandidate()
===================================

When a web site or app using [`RTCPeerConnection`](../rtcpeerconnection) receives a new ICE candidate from the remote peer over its signaling channel, it delivers the newly-received candidate to the browser's [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent by calling `RTCPeerConnection.addIceCandidate()`. This adds this new remote candidate to the `RTCPeerConnection`'s remote description, which describes the state of the remote end of the connection.

If the `candidate` parameter is missing or a value of `null` is given when calling `addIceCandidate()`, the added ICE candidate is an "end-of-candidates" indicator. The same is the case if the value of the specified object's [`candidate`](../rtcicecandidate/candidate) is either missing or an empty string (`""`), it signals that all remote candidates have been delivered.

The end-of-candidates notification is transmitted to the remote peer using a candidate with an a-line value of `end-of-candidates`.

During negotiation, your app will likely receive many candidates which you'll deliver to the ICE agent in this way, allowing it to build up a list of potential connection methods. This is covered in more detail in the articles [WebRTC connectivity](../webrtc_api/connectivity) and [Signaling and video calling](../webrtc_api/signaling_and_video_calling).

Syntax
------

    aPromise = pc.addIceCandidate(candidate);

    addIceCandidate(candidate, successCallback, failureCallback); 
        This deprecated API should no longer be used, but will probably still work.
        

### Parameters

 `candidate` <span class="badge inline optional">Optional</span>   
An object conforming to the [`RTCIceCandidateInit`](../rtcicecandidateinit) dictionary, or an [`RTCIceCandidate`](../rtcicecandidate) object; the contents of the object should be constructed from a message received over the signaling channel, describing a newly received ICE candidate that's ready to be delivered to the local ICE agent.

If no `candidate` object is specified, or its value is `null`, an end-of-candidates signal is sent to the remote peer using the `end-of-candidates` a-line, formatted like this:

    a=end-of-candidates

### Deprecated parameters

In older code and documentation, you may see a callback-based version of this function. This has been deprecated and its use is **strongly** discouraged. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `addIceCandidate()` instead. The parameters for this form of `addIceCandidate()` are described below, to aid in updating existing code.

 `successCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A function to be called when the ICE candidate has been successfully added. This function receives no input parameters and doesn't return a value.

 `failureCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A function to be called if attempting to add the ICE candidate fails. Receives as input a [`DOMException`](../domexception) object describing why failure occurred.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled when the candidate has been successfully added to the remote peer's description by the ICE agent. The promise does not receive any input parameters.

### Exceptions

When an error occurs while attempting to add the ICE candidate, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by this method is rejected, returning one of the errors below as the [`name`](../domexception/name) attribute in the specified [`DOMException`](../domexception) object passed to the rejection handler.

`TypeError`  
The specified candidate's [`sdpMid`](../rtcicecandidate/sdpmid) and [`sdpMLineIndex`](../rtcicecandidate/sdpmlineindex) are both `null`.

`InvalidStateError`  
The `RTCPeerConnection` currently has no remote peer established ([`remoteDescription`](remotedescription) is `null`).

`OperationError`  
This can happen for a number of reasons:

-   The value specified for [`sdpMid`](../rtcicecandidate/sdpmid) is non-`null` and doesn't match the media description ID of any media description included within the [`remoteDescription`](remotedescription).
-   The specified value of [`sdpMLineIndex`](../rtcicecandidate/sdpmlineindex) is greater than or equal to the number of media descriptions included in the remote description.
-   The specified [`ufrag`](../rtcicecandidate/usernamefragment) doesn't match the `ufrag` field in any of the remote descriptions being considered.
-   One or more of the values in the [`candidate`](../rtcicecandidate) string are invalid or could not be parsed.
-   Attempting to add the candidate fails for any reason.

Examples
--------

This code snippet shows how to signal ICE candidates across an arbitrary signaling channel.

    // This example assumes that the other peer is using a signaling channel as follows:
    //
    // pc.onicecandidate = event => {
    //   if (event.candidate) {
    //     signalingChannel.send(JSON.stringify({ice: event.candidate})); // "ice" is arbitrary
    //   } else {
    //     // All ICE candidates have been sent
    //   }
    // }

    signalingChannel.onmessage = receivedString => {
      const message = JSON.parse(receivedString);
      if (message.ice) {
        // A typical value of ice here might look something like this:
        //
        // {candidate: "candidate:0 1 UDP 2122154243 192.168.1.9 53421 typ host", sdpMid: "0", ...}
        //
        // Pass the whole thing to addIceCandidate:

        pc.addIceCandidate(message.ice).catch(e => {
          console.log("Failure during addIceCandidate(): " + e.name);
        });
      } else {
        // handle other things you might be signaling, like sdp
      }
    }

The last candidate to be signaled this way by the remote peer will be a special candidate denoting end-of-candidates. Out of interest, end-of-candidates may be manually indicated as follows:

    pc.addIceCandidate({candidate:''});

However, in most cases you won't need to look for this explicitly, since the events driving the [`RTCPeerConnection`](../rtcpeerconnection) will deal with it for you, sending the appropriate events.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-addicecandidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.addIceCandidate()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`addIceCandidate`

51

Promise-based version.

24

15

22

Starting in Firefox 68, the `candidate` parameter is optional when calling `addIceCandidate()`. A `null` value for `candidate` indicates no more candidates will be sent, while an empty `candidate` string indicates that no more candidates will be sent for the current generation of candidates.

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

Starting in Firefox 68, the `candidate` parameter is optional when calling `addIceCandidate()`. A `null` value for `candidate` indicates no more candidates will be sent, while an empty `candidate` string indicates that no more candidates will be sent for the current generation of candidates.

43

Promise-based version.

37-43

11

6.0

Promise-based version and unprefixed.

5.0-6.0

Promise-based version.

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)
-   [WebRTC architecture overview](../webrtc_api/protocols)
-   [WebRTC connectivity](../webrtc_api/connectivity)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addIceCandidate</a>
