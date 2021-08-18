MediaDevices: devicechange event
================================

A `devicechange` event is sent to a [`MediaDevices`](../mediadevices) instance whenever a media device such as a camera, microphone, or speaker is connected to or removed from the system. It's a generic [`Event`](../event) with no added properties.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><code>ondevicechange</code></td></tr></tbody></table>

Example
-------

You can use the `devicechange` event in an `addEventListener` method:

    navigator.mediaDevices.addEventListener('devicechange', function(event) {
      updateDeviceList();
    });

Or use the `ondevicechange` event handler property:

    navigator.mediaDevices.ondevicechange = function(event) {
      updateDeviceList();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediadevices-devicechange">Media Capture and Streams<br />
<span class="small">The definition of 'devicechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`devicechange_event`

57

12

52

No

34

11

No

No

?

43

11

No

See also
--------

-   [`MediaDevices.ondevicechange`](ondevicechange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/devicechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/devicechange_event</a>
