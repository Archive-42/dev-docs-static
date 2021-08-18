MediaStream.active
==================

The `active` read-only property of the [`MediaStream`](../mediastream) interface returns a Boolean value which is `true` if the stream is currently active; otherwise, it returns `false`. A stream is considered **active** if at least one of its [`MediaStreamTrack`](../mediastreamtrack)s is not in the <span class="page-not-created">`MediaStreamTrack.ended`</span> state. Once every track has ended, the stream's `active` property becomes `false`.

Syntax
------

    const isActive = MediaStream.active;

### Value

A Boolean value which is `true` if the stream is currently active; otherwise, the value is `false`.

Example
-------

In this example, a new stream whose source is the user's local camera and microphone is requested using [`getUserMedia()`](../mediadevices/getusermedia). When that stream becomes available (that is, when the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is fulfilled, a button on the page is updated based on whether or not the stream is currently active.

    const promise = navigator.mediaDevices.getUserMedia({
      audio: true,
      video: true
    });

    promise.then((stream) => {
      const startBtn = document.querySelector('#startBtn');
      startBtn.disabled = stream.active;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream-active">Media Capture and Streams<br />
<span class="small">The definition of 'active' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`active`

45

12

52

No

No

11

45

45

52

No

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/active" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/active</a>
