# BaseAudioContext.createConvolver()

The `createConvolver()` method of the [`BaseAudioContext`](../baseaudiocontext) interface creates a [`ConvolverNode`](../convolvernode), which is commonly used to apply reverb effects to your audio. See the [spec definition of Convolution](https://webaudio.github.io/web-audio-api/#background-3) for more information.

## Syntax

    baseAudioContext.createConvolver();

### Returns

A [`ConvolverNode`](../convolvernode).

## Example

The following example shows basic usage of an AudioContext to create a convolver node. The basic premise is that you create an AudioBuffer containing a sound sample to be used as an ambience to shape the convolution (called the _impulse response_,) and apply that to the convolver. The example below uses a short sample of a concert hall crowd, so the reverb effect applied is really deep and echoey.

For applied examples/information, check out our [Voice-change-O-matic demo](https://mdn.github.io/voice-change-o-matic/) ([see app.js](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js) for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var convolver = audioCtx.createConvolver();

      ...

    // grab audio track via XHR for convolver node

    var soundSource, concertHallBuffer;

    ajaxRequest = new XMLHttpRequest();
    ajaxRequest.open('GET', 'concert-crowd.ogg', true);
    ajaxRequest.responseType = 'arraybuffer';

    ajaxRequest.onload = function() {
      var audioData = ajaxRequest.response;
      audioCtx.decodeAudioData(audioData, function(buffer) {
          concertHallBuffer = buffer;
          soundSource = audioCtx.createBufferSource();
          soundSource.buffer = concertHallBuffer;
        }, function(e){"Error with decoding audio data" + e.err});
    }

    ajaxRequest.send();

      ...

    convolver.buffer = concertHallBuffer;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createconvolver">Web Audio API<br />
<span class="small">The definition of 'createConvolver()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createConvolver`

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

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createConvolver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createConvolver</a>
