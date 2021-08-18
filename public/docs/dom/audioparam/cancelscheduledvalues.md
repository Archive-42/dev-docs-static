# AudioParam.cancelScheduledValues()

The `cancelScheduledValues()` method of the [`AudioParam`](../audioparam) Interface cancels all scheduled future changes to the `AudioParam`.

## Syntax

    var AudioParam = AudioParam.cancelScheduledValues(startTime)

### Parameters

startTime  
A double representing the time (in seconds) after the [`AudioContext`](../audiocontext) was first created after which all scheduled changes will be cancelled.

### Returns

A reference to this `AudioParam` object. In some older implementations this method returns void.

## Examples

    var gainNode = audioCtx.createGain();
    gainNode.gain.setValueCurveAtTime(waveArray, audioCtx.currentTime, 2); //'gain' is the AudioParam
    gainNode.gain.cancelScheduledValues(audioCtx.currentTime);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-cancelscheduledvalues">Web Audio API<br />
<span class="small">The definition of 'cancelScheduledValues' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`cancelScheduledValues`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/cancelScheduledValues" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/cancelScheduledValues</a>
