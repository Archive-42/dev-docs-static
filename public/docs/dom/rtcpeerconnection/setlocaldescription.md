RTCPeerConnection.setLocalDescription()
=======================================

The [`RTCPeerConnection`](../rtcpeerconnection) method [`setLocalDescription()`](setlocaldescription) changes the local description associated with the connection. This description specifies the properties of the local end of the connection, including the media format. The method takes a single parameter—the session description—and it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the description has been changed, asynchronously.

If `setLocalDescription()` is called while a connection is already in place, it means renegotiation is underway (possibly to adapt to changing network conditions). Because descriptions will be exchanged until the two peers agree on a configuration, the description submitted by calling `setLocalDescription()` does not immediately take effect. Instead, the current connection configuration remains in place until negotiation is complete. Only then does the agreed-upon configuration take effect.

Syntax
------

    aPromise = RTCPeerConnection.setLocalDescription(sessionDescription);

    pc.setLocalDescription(sessionDescription, successCallback, errorCallback); 
        This deprecated API should no longer be used, but will probably still work.
        

### Parameters

 `sessionDescription` <span class="badge inline optional">Optional</span>   
An <span class="page-not-created">`RTCSessionDescriptionInit`</span> or [`RTCSessionDescription`](../rtcsessiondescription) which specifies the configuration to be applied to the local end of the connection. If the description is omitted, the WebRTC runtime tries to automatically do the right thing.

#### Implicit description

If you don't explicity provide a session description, the WebRTC runtime will try to handle it correctly. If the signaling state is one of `stable`, `have-local-offer`, or `have-remote-pranswer`, the WebRTC runtime automatically creates a new offer and sets that as the new local description. Otherwise, `setLocalDescription()` creates an answer, which becomes the new local description.

#### Type of the description parameter

The description is of type `RTCSessionDescriptionInit`, which is a serialized version of a [`RTCSessionDescription`](../rtcsessiondescription) browser object. They're interchangeable:

    myPeerConnection.createOffer().then(function(offer) {
      return myPeerConnection.setLocalDescription(offer);
    });

This is equivalent to:

    myPeerConnection.createOffer().then(function(offer) {
      return myPeerConnection.setLocalDescription(new RTCSessionDescription(offer));
    });

For this reason, the [`RTCSessionDescription()`](../rtcsessiondescription/rtcsessiondescription) constructor is deprecated.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the value of [`RTCPeerConnection.localDescription`](localdescription) is successfully changed or rejected if the change cannot be applied (for example, if the specified description is incompatible with one or both of the peers on the connection). The promise's fulfillment handler receives no input parameters.

The process of changing descriptions actually involves intermediary steps handled by the WebRTC layer to ensure that an active connection can be changed without losing the connection if the change does not succeed. See [Pending and current descriptions](#) in [WebRTC connectivity](../webrtc_api/connectivity) for more details on this process.

### Deprecated parameters

In older code and documentation, you may see a callback-based version of this function used. This has been deprecated and its use is **strongly** discouraged, as it will be removed in the future. You should update any existing code to use the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of `setLocalDescription()` instead. The parameters for the older form of `setLocalDescription()` are described below, to aid in updating existing code.

 `successCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A JavaScript [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) which accepts no input parameters to be called once the description has been successfully set. At that time, the offer can be sent to a remote peer via the signaling server.

 `errorCallback` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A function matching the signature `RTCPeerConnectionErrorCallback` which gets called if the description can't be set. It is passed a single [`DOMException`](../domexception) object explaining why the request failed.

This deprecated form of the method returns instantaneously without waiting for the actual setting to be done: in case of success, the `successCallback` will be called; in case of failure, the `errorCallback` will be called.

### Deprecated exceptions

When using the deprecated callback-based version of `setLocalDescription()`, the following exceptions may occur:

 `InvalidStateError` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The connection's [`signalingState`](signalingstate) is `"closed"`, indicating that the connection is not currently open, so negotiation cannot take place.

 `InvalidSessionDescriptionError` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The [`RTCSessionDescription`](../rtcsessiondescription) specified by the `sessionDescription` parameter is invalid.

Examples
--------

### Implicit descriptions

One of the advantages of the parameter-free form of `setLocalDescription()` is that it lets you simplify your negotiation code substantially. This is all your [`negotiationneeded`](negotiationneeded_event) event handler needs to look like, for the most part. Just add the signaling server code, which here is represented by the call to `signalRemotePeer()`.

    pc.addEventListener("negotiationneeded", async (event) => {
      await pc.setLocalDescription();
      signalRemotePeer({ description: pc.localDescription });
    });

Other than error handling, that's about it!

### Providing your own offer or answer

The example below shows the implementation of a handler for the `negotiationneeded` event that explicitly creates an offer, rather than letting `setLocalDescription()` do it.

    async function handleNegotiationNeededEvent() {
      try {
        const offer = await pc.createOffer();
        pc.setLocalDescription(offer);
        signalRemotePeer({ description: pc.localDescription });
      } catch(err) {
        reportError(err);
      }
    }

This begins by creating an offer by calling [`createOffer()`](createoffer); when that succeeds, we call `setLocalDescription()`. We can then send the newly-created offer along to the other peer using the signaling server, which here is done by calling a function called `signalRemotePeer()`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-setlocaldescription">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.setLocalDescription()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setLocalDescription`

51

Promise-based version.

24

15

22

Firefox does not support descriptions of type `pranswer`.

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

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setLocalDescription</a>
