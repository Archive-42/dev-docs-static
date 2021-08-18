# BaseAudioContext.currentTime

The `currentTime` read-only property of the [`BaseAudioContext`](../baseaudiocontext) interface returns a double representing an ever-increasing hardware timestamp in seconds that can be used for scheduling audio playback, visualizing timelines, etc. It starts at 0.

## Syntax

    var curTime = baseAudioContext.currentTime;

## Example

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();
    // Older webkit/blink browsers require a prefix

    ...

    console.log(audioCtx.currentTime);

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `audioCtx.currentTime` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    audioCtx.currentTime;
    // 23.404
    // 24.192
    // 25.514
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    audioCtx.currentTime;
    // 49.8
    // 50.6
    // 51.7
    // ...

In Firefox, you can also enabled `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-currenttime">Web Audio API<br />
<span class="small">The definition of 'currentTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`currentTime`

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

6

1.0

## See also

- [Using Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/currentTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/currentTime</a>
