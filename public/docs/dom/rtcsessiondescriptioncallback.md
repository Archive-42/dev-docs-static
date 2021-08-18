RTCSessionDescriptionCallback
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCSessionDescriptionCallback` type is used to represent the callback function passed into the deprecated callback-based version of [`createOffer()`](rtcpeerconnection/createoffer) or [`createAnswer()`](rtcpeerconnection/createanswer) when using them to create offers or answers.

Because this function type is part of the legacy WebRTC API, you should avoid using it (and the callback-based forms of `createOffer()` and `createAnswer()` that make use of it).

Syntax
------

    RTCSessionDescriptionCallback(description);

### Parameters

`description`  
An <span class="page-not-created">`RTCSessionDescriptionInit`</span> (or [`RTCSessionDescription`](rtcsessiondescription)) object describing the session being offered or being accepted. This object contains the `type` and `sdp` properties which are part of [`RTCSessionDescription`](rtcsessiondescription).

### Return value

The callback doesn't need to return anything, so the return value is `undefined`.

Example
-------

    var pc = new RTCPeerConnection();
    var descriptionCallback = function(offer) {
      pc.setLocalDescription(offer);
    }
    pc.createOffer(descriptionCallback);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcsessiondescriptioncallback">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescriptionCallback' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCSessionDescriptionCallback`

Yes

≤18

22

No

?

?

Yes

Yes

24

?

?

Yes

See also
--------

-   [WebRTC API](webrtc_api)
-   [Lifetime of a WebRTC connection](webrtc_api/session_lifetime)
-   [`RTCPeerConnection`](rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescriptionCallback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescriptionCallback</a>
