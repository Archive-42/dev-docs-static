RTCIceCandidate. toJSON()
=========================

The [`RTCIceCandidate`](../rtcicecandidate) method `toJSON()` converts the `RTCIceCandidate` on which it's called into JSON in the form of an [`RTCIceCandidateInit`](../rtcicecandidateinit) object.

Syntax
------

    json = rtcIceCandidate.toJSON();

### Return value

An object conforming to the [`RTCIceCandidateInit`](../rtcicecandidateinit) dictionary, whose members' values are set to the corresponding values in the `RTCIceCandidate` object.

You can then get a stringified version of the object by calling [`stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) on the returned object. See the [example](#example) below.

Example
-------

This simple example obtains a JSON string representing an `RTCIceCandidate` found in the variable `candidate`.

    var jsonString = candidate.toJSON().stringify();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-tojson">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.toJSON()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toJSON`

45

15

27

No

32

11

45

45

27

32

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/toJSON</a>
