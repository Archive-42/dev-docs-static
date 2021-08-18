# AudioParam.setValueCurveAtTime()

The `setValueCurveAtTime()` method of the [`AudioParam`](../audioparam) interface schedules the parameter's value to change following a curve defined by a list of values. The curve is a linear interpolation between the sequence of values defined in an array of floating-point values, which are scaled to fit into the given interval starting at `startTime` and a specific duration.

## Syntax

    var paramRef = param.setValueCurveAtTime(values, startTime, duration);

### Parameters

`values`  
An array of floating-point numbers representing the value curve the [`AudioParam`](../audioparam) will change through along the specified `duration`. Every value in the array must be a finite number; if any value is `NaN`, `Infinity`, or `-Infinity`, a `TypeError` exception is thrown.

`startTime`  
A double representing the time (in seconds) after the [`AudioContext`](../audiocontext) was first created that the change in value will happen. If this value is lower than [`AudioContext.currentTime`](../baseaudiocontext/currenttime), it is clamped to `currentTime`.

`duration`  
A double representing the total time (in seconds) over which the parameter's `value` will change following the specified curve. The specified values are spaced equally along this duration.

### Return value

A reference to this `AudioParam` object. Some older browser implementations of this interface return `undefined`.

### Exceptions

`InvalidStateError`  
The specified array of `values` has fewer than 2 items in it.

`RangeError`  
The specified `startTime` is either negative or a non-finite value, or `duration` is not a finite, strictly positive number.

`TypeError`  
One or more of the values in the `values` array is non-finite. Non-finite values are `NaN`, `Infinity`, and `-Infinity`.

## Usage notes

When the parameter's value finishes following the curve, its value is guaranteed to match the last value in the set of values specified in the `values` parameter.

**Note:** Some early implementations of the Web Audio API did not ensure this to be the case, causing unexpected results.

## Examples

In this example, we have a media source with a single button (see the [webaudio-examples repo](https://github.com/mdn/webaudio-examples/blob/master/audio-param/index.html) for the source code, or [view the example live](https://mdn.github.io/webaudio-examples/audio-param/).) When this button is pressed, `setValueCurveAtTime()` is used to change the gain value between the values contained in the waveArray array:

    // create audio context
    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    // set basic variables for example
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    var valueCurve = document.querySelector('.value-curve');

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a gain node and set it's gain value to 0.5
    var gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.5;
    var currGain = gainNode.gain.value;

    // connect the AudioBufferSourceNode to the gainNode
    // and the gainNode to the destination
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    // set button to do something onclick

    var waveArray = new Float32Array(9);
    waveArray[0] = 0.5;
    waveArray[1] = 1;
    waveArray[2] = 0.5;
    waveArray[3] = 0;
    waveArray[4] = 0.5;
    waveArray[5] = 1;
    waveArray[6] = 0.5;
    waveArray[7] = 0;
    waveArray[8] = 0.5;

    valueCurve.onclick = function() {
      gainNode.gain.setValueCurveAtTime(waveArray, audioCtx.currentTime, 2);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-setvaluecurveattime">Web Audio API<br />
<span class="small">The definition of 'setValueCurveAtTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setValueCurveAtTime`

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

Versions before Chrome 46 use nearest neighbor instead of linear interpolation.

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setValueCurveAtTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/setValueCurveAtTime</a>
