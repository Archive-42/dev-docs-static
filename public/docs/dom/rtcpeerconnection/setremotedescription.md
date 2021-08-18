RTCPeerConnection.setRemoteDescription()
========================================

The [`RTCPeerConnection`](../rtcpeerconnection) method `setRemoteDescription()` sets the specified session description as the remote peer's current offer or answer. The description specifies the properties of the remote end of the connection, including the media format. The method takes a single parameter—the session description—and it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the description has been changed, asynchronously.

This is typically called after receiving an offer or answer from another peer over the signaling server. Keep in mind that if `setRemoteDescription()` is called while a connection is already in place, it means renegotiation is underway (possibly to adapt to changing network conditions).

Because descriptions will be exchanged until the two peers agree on a configuration, the description submitted by calling `setRemoteDescription()` does not immediately take effect. Instead, the current connection configuration remains in place until negotiation is complete. Only then does the agreed-upon configuration take effect.

Syntax
------

    aPromise = rtcPeerConnection.setRemoteDescription(sessionDescription);

### Parameters

`sessionDescription`  
An <span class="page-not-created">`RTCSessionDescriptionInit`</span> or [`RTCSessionDescription`](../rtcsessiondescription) which specifies the remote peer's current offer or answer. This value is an offer or answer received from the remote peer through your implementation of

The `sessionDescription` parameter is technically of type `RTCSessionDescriptionInit`, but because [`RTCSessionDescription`](../rtcsessiondescription) serializes to be indistinguishable from `RTCSessionDescriptionInit`, you can also pass in an `RTCSessionDescription`. This lets you simplify code such as the following:

    myPeerConnection.setRemoteDescription(new RTCSessionDescription(description))
    .then(function () {
      return createMyStream();
    })

to be:

    myPeerConnection.setRemoteDescription(description)
    .then(function () {
      return createMyStream();
    })

Using `async`/`await` syntax, you can further simplify this to:

    await myPeerConnection.setRemoteDescription(description);
    createMyStream();

Since it's unnecessary, the [`RTCSessionDescription()`](../rtcsessiondescription/rtcsessiondescription) constructor is deprecated.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the value of the connection's [`remoteDescription`](remotedescription) is successfully changed or rejected if the change cannot be applied (for example, if the specified description is incompatible with one or both of the peers on the connection). The promise fulfillment handler receives no input parameters.

**Note:** The process of changing descriptions actually involves intermediary steps handled by the WebRTC layer to ensure that an active connection can be changed without losing the connection if the change does not succeed. See [Pending and current descriptions](#) in [WebRTC connectivity](../webrtc_api/connectivity) for more details on this process.

### Exceptions

The following exceptions are reported to the rejection handler for the promise returned by `setRemoteDescription()`:

`InvalidAccessError`  
The content of the description is invalid.

`InvalidStateError`  
The [`RTCPeerConnection`](../rtcpeerconnection) is closed, or it's in a state which isn't compatible with the specified description's [`type`](../rtcsessiondescription/type). For example, if the `type` is `rollback` and the signaling state is one of `stable`, `have-local-pranswer`, or `have-remote-pranswer`, this exception is thrown, because you can't roll back a connection that's either fully established or is in the final stage of becoming connected.

`OperationError`  
Any errors that occur which don't match the others specifeid here are reported as `OperationError`. This includes identity validation errors.

`RTCError`  
An `RTCError` with the [`errorDetail`](../rtcerror/errordetail) set to `sdp-syntax-error` is reported if the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) specified by [`RTCSessionDescription.sdp`](../rtcsessiondescription/sdp). The error object's [`sdpLineNumber`](../rtcerror/sdplinenumber) property indicates the line number within the SDP on which the syntax error was detected.

`TypeError`  
The specified `RTCSessionDescriptionInit` or `RTCSessionDescription` object is missing the [`type`](../rtcsessiondescription/type) property, or no description parameter was provided at all.

Usage notes
-----------

When you call `setRemoteDescription()`, the ICE agent checks to make sure the [`RTCPeerConnection`](../rtcpeerconnection) is in either the `stable` or `have-remote-offer` [`signalingState`](signalingstate). These states indicate that either an existing connection is being renegotiated or that an offer previously specified by an earlier call to `setRemoteDescription()` is to be replaced with the new offer. In either of those two cases, we're at the beginning of the negotiation process, and the offer is set as the remote description.

On the other hand, if we're in the middle of an ongoing negotiation and an offer is passed into `setRemoteDescription()`, the ICE agent automatically begins an ICE rollback in order to return the connection to a stable signaling state, then, once the rollback is completed, sets the remote description to the specified offer. This begins a new negotiation session, with the newly-established offer as the starting point.

Upon starting the new negotiation with the newly-established offer, the local peer is now the callee, even if it was previously the caller. This happens instead of throwing an exception, thereby reducing the number of potential errors which might occur, and simplifies the processing you need to do when you receive an offer, by eliminating the need to handle the offer/answer process differently depending on whether the local peer is the caller or callee.

**Note:** Earlier implementations of WebRTC would throw an exception if an offer was set outside a `stable` or `have-remote-offer` state.

Deprecated syntax
-----------------

In older code and documentation, you may see a callback-based version of this function used. This has been deprecated and its use is *strongly* discouraged. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `setRemoteDescription()` instead. The parameters for the older form of `setRemoteDescription()` are described below, to aid in updating existing code.

    pc.setRemoteDescription(sessionDescription, successCallback, errorCallback);

### Parameters

 `successCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A JavaScript [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) which accepts no input parameters to be called once the description has been successfully set. At that time, the offer can be sent to a remote peer via the signaling server.

 `errorCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A function matching the signautre `RTCPeerConnectionErrorCallback` which gets called if the description can't be set. It is passed a single [`DOMException`](../domexception) object explaining why the request failed.

This deprecated form of the method returns instantaneously without waiting for the actual setting to be done: in case of success, the `successCallback` will be called; in case of failure, the `errorCallback` will be called.

### Exceptions

When using the deprecated callback-based version of `setRemoteDescription()`, the following exceptions may occur:

 `InvalidStateError` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The connection's [`signalingState`](signalingstate) is `"closed"`, indicating that the connection is not currently open, so negotiation cannot take place.

 `InvalidSessionDescriptionError` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The [`RTCSessionDescription`](../rtcsessiondescription) specified by the `sessionDescription` parameter is invalid.

Example
-------

Here we see a function which handles an offer received from the remote peer. This code is derived from the example and tutorial in the article [Signaling and video calling](../webrtc_api/signaling_and_video_calling); take a look at that for more details and a more in-depth explanation of what's going on.

    function handleOffer(msg) {
      createMyPeerConnection();

      myPeerConnection.setRemoteDescription(msg.description).then(function () {
        return navigator.mediaDevices.getUserMedia(mediaConstraints);
      })
      .then(function(stream) {
        document.getElementById("local_video").srcObject = stream;
        return myPeerConnection.addStream(stream);
      })
      .then(function() {
        return myPeerConnection.createAnswer();
      })
      .then(function(answer) {
        return myPeerConnection.setLocalDescription(answer);
      })
      .then(function() {
        // Send the answer to the remote peer using the signaling server
      })
      .catch(handleGetUserMediaError);
    }

After creating our [`RTCPeerConnection`](../rtcpeerconnection) and saving it as `myPeerConnection`, we pass the description included in the received offer message, `msg`, directly into `setRemoteDescription()` to tell the user agent's WebRTC layer what configuration the caller has proposed using. When our promise fulfillment handler is called, indicating that this has been done, we create a stream, add it to the connection, then create an SDP answer and call [`setLocalDescription()`](setlocaldescription) to set that as the configuration at our end of the call before forwarding that answer to the caller.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-setremotedescription">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.setRemoteDescription()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setRemoteDescription`

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

5.0

Promise-based version.

Yes

`implicit_rollback`

80

80

70

No

No

No

80

80

No

No

No

13.0

`optional_description`

80

80

75

No

No

No

80

80

No

No

No

13.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCPeerConnection.remoteDescription`](remotedescription), [`RTCPeerConnection.pendingRemoteDescription`](pendingremotedescription), [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setRemoteDescription</a>
