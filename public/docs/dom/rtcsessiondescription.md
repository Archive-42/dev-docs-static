RTCSessionDescription
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCSessionDescription` interface describes one end of a connection—or potential connection—and how it's configured. Each `RTCSessionDescription` consists of a description [`type`](rtcsessiondescription/type) indicating which part of the offer/answer negotiation process it describes and of the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) descriptor of the session.

The process of negotiating a connection between two peers involves exchanging `RTCSessionDescription` objects back and forth, with each description suggesting one combination of connection configuration options that the sender of the description supports. Once the two peers agree upon a configuration for the connection, negotiation is complete.

Properties
----------

*The `RTCSessionDescription` interface doesn't inherit any properties.*

 [`RTCSessionDescription.type`](rtcsessiondescription/type) <span class="badge inline readonly">Read only </span>   
An enum of type `RTCSdpType` describing the session description's type.

 [`RTCSessionDescription.sdp`](rtcsessiondescription/sdp) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) containing the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) describing the session.

Constants
---------

### RTCSdpType

This enum defines strings that describe the current state of the session description, as used in the [`type`](rtcsessiondescription/type) property. The session description's type will be specified using one of these values.

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>answer</code></td><td>The SDP contained in the <a href="rtcsessiondescription/sdp"><code>sdp</code></a> property is the definitive choice in the exchange. In other words, this session description describes the agreed-upon configuration, and is being sent to finalize negotiation.</td></tr><tr class="even"><td><code>offer</code></td><td>The session description object describes the initial proposal in an offer/answer exchange. The session negotiation process begins with an offer being sent from the caller to the callee.</td></tr><tr class="odd"><td><code>pranswer</code></td><td>The session description object describes a provisional answer; that is, a response to a previous offer that is not the final answer. It is usually employed by legacy hardware.</td></tr><tr class="even"><td><code>rollback</code></td><td>This special type with an empty session description is used to roll back to the previous stable state.</td></tr></tbody></table>

Methods
-------

*The `RTCSessionDescription` doesn't inherit any methods.*

 [`RTCSessionDescription()`](rtcsessiondescription/rtcsessiondescription) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This constructor returns a new `RTCSessionDescription`. The parameter is a `RTCSessionDescriptionInit` dictionary containing the values to assign the two properties.

[`RTCSessionDescription.toJSON()`](rtcsessiondescription/tojson)  
Returns a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) description of the object. The values of both properties, [`type`](rtcsessiondescription/type) and [`sdp`](rtcsessiondescription/sdp), are contained in the generated JSON.

Example
-------

    signalingChannel.onmessage = function (evt) {
        if (!pc)
            start(false);

        var message = JSON.parse(evt.data);
        if (message.sdp)
            pc.setRemoteDescription(new RTCSessionDescription(message), function () {
                // if we received an offer, we need to answer
                if (pc.remoteDescription.type == "offer")
                    pc.createAnswer(localDescCreated, logError);
            }, logError);
        else
            pc.addIceCandidate(new RTCIceCandidate(message.candidate),
                function () {}, logError);
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcsessiondescription-class">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescription' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

Yes

14

11

1.5

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

`sdp`

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

`toJSON`

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

-   [WebRTC](webrtc_api)
-   [`RTCPeerConnection.setLocalDescription()`](rtcpeerconnection/setlocaldescription) and [`RTCPeerConnection.setRemoteDescription()`](rtcpeerconnection/setremotedescription)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription</a>
