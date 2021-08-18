# RTCIceCandidate.candidate

The read-only property `candidate` on the [`RTCIceCandidate`](../rtcicecandidate) interface returns a [`DOMString`](../domstring) describing the candidate in detail. Most of the other properties of `RTCIceCandidate` are actually extracted from this string.

This property can be configured by specifying the value of the [`candidate`](../rtcicecandidateinit/candidate) property when constructing the new candidate object using [`RTCIceCandidate()`](rtcicecandidate).

## Syntax

    var candidate = RTCIceCandidate.candidate;

### Value

A [`DOMString`](../domstring) describing the properties of the candidate, taken directly from the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) attribute `"candidate"`. The candidate string specifies the network connectivity information for the candidate. If the `candidate` is an empty string (`""`), the end of the candidate list has been reached; this candidate is known as the "end-of-candidates" marker.

The syntax of the candidate string is described in [RFC 5245, section 15.1](https://tools.ietf.org/html/rfc5245#section-15.1). For an a-line (attribute line) that looks like this:

    a=candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host

the corresponding `candidate` string's value will be `"candidate:4234997325 1 udp 2043278322 192.168.0.56 44323 typ host"`.

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) always prefers candidates with the highest [`priority`](priority), all else being equal. In the example above, the priority is `2043278322`. The attributes are all separated by a single space character, and are in a specific order. The complete list of attributes for this example candidate is:

- [`foundation`](foundation) = 4234997325
- [`component`](component) = `"rtp"` (the number 1 is encoded to this string; 2 becomes `"rtcp"`)
- [`protocol`](protocol) = `"udp"`
- [`priority`](priority) = 2043278322
- [`ip`](address) = `"192.168.0.56"`
- [`port`](port) = 44323
- [`type`](type) = `"host"`

## Example

In this example, we see a function which receives as input an SDP string containing an ICE candidate received from the remote peer during the signaling process.

    function handleNewIceCandidate(candidateSDP) {
      var candidateObj = new RTCIceCandidate(candidateSDP);

      myPeerConnection.addIceCandidate(candidateObj).catch({
        /* handle the error thrown by addIceCandidate() */
      });
    }

The `handleNewIceCandidate()` function shown here passes the received candidate's SDP text into [`RTCIceCandidate()`](rtcicecandidate) to receive an <span class="page-not-created">`RTCIceCanddiate`</span> object in return, which represents the candidate.

The new candidate is then passed into [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate) to add the candidate to the list of candidates for WebRTC to consider using for the connection being established.

This example could be simplified somewhat; you may more often see the code look something like this, taking advantage of more advanced ECMAScript 2016 features:

    let handleNewIceCandidate = candidateSDP =>
      myPeerConnection.addIceCandidate(new RTCIceCandidate(candidateSDP));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-candidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.candidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`candidate`

23

15

22

No

15

11

≤37

25

Yes

14

11

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/candidate</a>
