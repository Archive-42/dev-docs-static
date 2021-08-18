RTCSessionDescription.type
==========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The property `RTCSessionDescription.type` is a read-only value of type `RTCSdpType` which describes the description's type.

Syntax
------

    var value = sessionDescription.type;
    sessionDescription.type = value;

### Value

The possible values are defined by an enum of type RTCSdpType.

The allowed values are those of an enum of type `RTCSdpType`:

-   `"offer"`, the description is the initial proposal in an offer/answer exchange.
-   `"answer"`, the description is the definitive choice in an offer/answer exchange.
-   `"pranswer"`, the description is a provisional answer and may be changed when the definitive choice will be given.
-   "`rollback`", the description rolls back to offer/answer state to the last stable state.

Example
-------

    // The remote description has been set previously on pc, a RTCPeerconnection

    alert(pc.remoteDescription.type);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcsessiondescription-type">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescription.type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`type`

Yes

15

Yes

No

Yes

11

Yes

Yes

Yes

Yes

11

Yes

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/type</a>
