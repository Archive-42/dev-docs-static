RTCSessionDescription.toJSON()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCSessionDescription.toJSON()` method generates a [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) description of the object. Both properties, [`type`](type) and [`sdp`](sdp), are contained in the generated JSON.

Syntax
------

    var jsonValue = sd.toJSON();

The result value is a [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) object containing the following values:

-   `"type"`, containing the value of the [`RTCSessionDescription.type`](type) property and can be one of the following values: `"offer"`, `"answer"`, `"pranswer"` or `null`.
-   `"sdp"`, containing a [`DOMString`](../domstring), or `null`, with the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) message corresponding to [`RTCSessionDescription.sdp`](sdp) property.

Example
-------

    // sd is a RTCSessionDescriptor

    alert(JSON.stringify(sd)); // This call the toJSON() method behind the scene.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcsessiondescription-tojson">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCSessionDescription: toJSON()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCSessionDescription/toJSON</a>
