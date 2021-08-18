RTCSessionDescription()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCSessionDescription()` constructor creates a new [`RTCSessionDescription`](../rtcsessiondescription) with its properties initialized as described in the specified object.

This constructor has been deprecated because [`RTCPeerConnection.setLocalDescription()`](../rtcpeerconnection/setlocaldescription) and other methods which take SDP as input now directly accept an object conforming to the `RTCSessionDescriptionInit` dictionary, so you don't have to instantiate an `RTCSessionDescription` yourself.

Syntax
------

     sessionDescription = new RTCSessionDescription(rtcSessionDescriptionInit);

### Values

 `rtcSessionDescriptionInit` <span class="badge inline optional">Optional</span>   
An object providing the default values for the session description; the object conforms to the `RTCSessionDescriptionInit` dictionary. That dictionary has the following properties:

`type`  
**Required.** A string which is a member of the `RTCSdpType` enum; it must have one of the following values:

This enum defines strings that describe the current state of the session description, as used in the [`type`](type) property. The session description's type will be specified using one of these values.

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>answer</code></td><td>The SDP contained in the <a href="sdp"><code>sdp</code></a> property is the definitive choice in the exchange. In other words, this session description describes the agreed-upon configuration, and is being sent to finalize negotiation.</td></tr><tr class="even"><td><code>offer</code></td><td>The session description object describes the initial proposal in an offer/answer exchange. The session negotiation process begins with an offer being sent from the caller to the callee.</td></tr><tr class="odd"><td><code>pranswer</code></td><td>The session description object describes a provisional answer; that is, a response to a previous offer that is not the final answer. It is usually employed by legacy hardware.</td></tr><tr class="even"><td><code>rollback</code></td><td>This special type with an empty session description is used to roll back to the previous stable state.</td></tr></tbody></table>

`sdp`  
A string containing a [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) message describing the session. This value is an empty string (`""`) by default and may not be `null`.

Example
-------

This example uses the constructor to convert an SDP offer into an `RTCSessionDescription` object.

This is no longer necessary, however; [`RTCPeerConnection.setLocalDescription()`](../rtcpeerconnection/setlocaldescription) and other methods which take SDP as input now directly accept an object conforming to the `RTCSessionDescriptionInit` dictionary, so you don't have to instantiate an `RTCSessionDescription` yourself.

    navigator.getUserMedia({video: true}, function(stream) {
      pc.onaddstream({stream: stream});
      // Adding a local stream won't trigger the onaddstream callback
      pc.addStream(stream);

      pc.createOffer(function(offer) {
        pc.setLocalDescription(new RTCSessionDescription(offer), function() {
          // send the offer to a server to be forwarded to the friend you're calling.
        }, error);
      }, error);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#widl-ctor-RTCSessionDescription--RTCSessionDescriptionInit-descriptionInitDict">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescription()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`RTCSessionDescription`

23

15

Yes

No

15

11

≤37

25

?

14

11

1.5

See also
--------

-   [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API)
-   [`RTCSessionDescription`](../rtcsessiondescription)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/RTCSessionDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/RTCSessionDescription</a>
