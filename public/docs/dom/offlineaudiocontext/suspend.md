OfflineAudioContext.suspend()
=============================

The `suspend()` method of the [`OfflineAudioContext`](../offlineaudiocontext) interface schedules a suspension of the time progression in the audio context at the specified time and returns a promise. This is generally useful at the time of manipulating the audio graph synchronously on OfflineAudioContext.

Note that the maximum precision of suspension is the size of the render quantum and the specified suspension time will be rounded down to the nearest render quantum boundary. For this reason, it is not allowed to schedule multiple suspends at the same quantized frame. Also scheduling should be done while the context is not running to ensure the precise suspension.

Syntax
------

    OfflineAudioContext.suspend(suspendTime).then(function() { ... });

### Parameters

suspendTime  
A <span class="page-not-created">`double`</span> specifying the suspend time, in seconds.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolving to void.

### Exceptions

The promise is rejected when any exception is encountered.

[`InvalidStateError`](../domexception#exception-invalidstateerror) if the quantized frame number is one of the following:

-   a negative number
-   is less than or equal to the current time
-   is greater than or equal to the total render duration
-   is scheduled by another suspend for the same time

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocontext-suspend">Web Audio API<br />
<span class="small">The definition of 'suspend()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`suspend`

49

≤18

No

No

36

14.1

49

49

No

36

14.5

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/suspend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/suspend</a>
