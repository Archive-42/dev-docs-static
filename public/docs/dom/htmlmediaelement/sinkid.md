HTMLMediaElement.sinkId
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLMediaElement.sinkId` read-only property returns a [`DOMString`](../domstring) that is the unique ID of the audio device delivering output. If it is using the user agent default, it returns an empty string. This ID should be one of the [`MediaDeviceInfo.deviceId`](../mediadeviceinfo/deviceid) values returned from [`MediaDevices.enumerateDevices()`](../mediadevices/enumeratedevices), `id-multimedia`, or `id-communications`.

Syntax
------

    var sinkId = HTMLMediaElement.sinkId

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-output/#dom-htmlmediaelement-sinkid">Audio Output Devices API<br />
<span class="small">The definition of 'sinkId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. Older versions of this spec were called "Media Capture Output".</td></tr></tbody></table>

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

`sinkId`

49

17

No

No

36

No

No

49

No

?

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/sinkId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/sinkId</a>
