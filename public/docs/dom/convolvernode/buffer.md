# ConvolverNode.buffer

The `buffer` property of the [`ConvolverNode`](../convolvernode) interface represents a mono, stereo, or 4-channel [`AudioBuffer`](../audiobuffer) containing the (possibly multichannel) impulse response used by the `ConvolverNode` to create the reverb effect.

This is normally a simple recording of as-close-to-an-impulse as can be found in the space you want to model. For example, if you want to model the reverb in your bathroom, you might set up a microphone near the door to record the sound of a balloon pop or synthesized impulse from the sink. That audio recording could then be used as the buffer.

This _[`AudioBuffer`](../audiobuffer)_ must have the same sample-rate as the `AudioContext` or an exception will be thrown. At the time when this attribute is set, the buffer and the state of the attribute will be used to configure the `ConvolverNode` with this impulse response having the given normalization. The initial value of this attribute is `null`.

## Syntax

    var audioCtx = new AudioContext();
    var convolver = audioCtx.createConvolver();
    convolver.buffer = myAudioBuffer;

### Value

An [`AudioBuffer`](../audiobuffer).

## Example

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-convolvernode-buffer">Web Audio API<br />
<span class="small">The definition of 'buffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`buffer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/buffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/buffer</a>
