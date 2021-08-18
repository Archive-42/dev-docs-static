# HTMLMediaElement.setSinkId()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLMediaElement.setSinkId()` method sets the ID of the audio device to use for output and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). This only works when the application is authorized to use the specified device.

## Syntax

    HTMLMediaElement.setSinkId(sinkId).then(function() { ... })

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Parameters

sinkId  
The [`MediaDeviceInfo.deviceId`](../mediadeviceinfo/deviceid) of the audio output device.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><a href="../domexception"><code>DOMException</code></a></td><td>No permission to use the requested device</td></tr></tbody></table>

## Examples

    const devices = await navigator.mediaDevices.enumerateDevices();
    const audioDevices = devices.filter(device => device.kind === 'audiooutput');
    const audio = document.createElement('audio');
    await audio.setSinkId(audioDevices[0].deviceId);
    console.log('Audio is being played on ' + audio.sinkId);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-output/#dom-htmlmediaelement-setsinkid">Audio Output Devices API<br />
<span class="small">The definition of 'sinkId' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. Older versions of this spec were called "Media Capture Output".</td></tr></tbody></table>

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

`setSinkId`

49

17

64

No

36

No

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

64

36

No

No

Not availabe due to [a limitation in Android](https://crbug.com/648286).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setSinkId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/setSinkId</a>
