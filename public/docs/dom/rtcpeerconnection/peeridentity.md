RTCPeerConnection.peerIdentity
==============================

The read-only [`RTCPeerConnection`](../rtcpeerconnection) property `peerIdentity` returns a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an [`RTCIdentityAssertion`](../rtcidentityassertion) which contains a [`DOMString`](../domstring) identifying the remote peer. Once this promise resolves successfully, the resulting identity is the **target peer identity** and cannot change for the duration of the connection.

Syntax
------

     var identity = rtcPeerConnection.peerIdentity;

### Value

A JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`RTCIdentityAssertion`](../rtcidentityassertion) that describes the remote peer's identity.

If an error occcurs while attempting to validate an incoming identity assertion (that is, the information describing a peer's identity), the promise is rejected. If there isn't already a target peer identity, `peerIdentity` is set to a newly created promise and the process begins again, until the process succeeds or no further attempts to authenticate occur.

**Note:** The promise returned by [`setRemoteDescription()`](setremotedescription) cannot resolve until any target peer identity that's been set is validated. If the identity hasn't been validated yet, the promise returned by `setRemoteDescription()` will be rejected. If there's no target peer identity, `setRemoteDescription()` doesn't need to wait for validation to occur before it resolves.

Example
-------

In this example, a function, `getIdentityAssertion()`, is created which asynchronously waits for the peer's identity to be verified, then returns the identity to the caller. If an error occurs and the promise is rejected, this logs the error to the console and returns `null` to the caller.

    let pc = new RTCPeerConnection();

    /* ... */

    async function getIdentityAssertion(pc) {
      try {
        const identity = await pc.peerIdentity;
        return identity;
      } catch(err) {
        console.log("Error identifying remote peer: ", err);
        return null;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-identity/#dfn-peeridentity">Identity for WebRTC</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`peerIdentity`

No

≤18-79

22

No

43

Promise-based version.

37-43

No

No

No

44

43

Promise-based version.

37-43

No

6.0

See also
--------

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/peerIdentity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/peerIdentity</a>
