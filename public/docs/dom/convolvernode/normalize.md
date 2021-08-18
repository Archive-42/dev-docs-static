# ConvolverNode.normalize

The `normalize` property of the [`ConvolverNode`](../convolvernode) interface is a boolean that controls whether the impulse response from the buffer will be scaled by an equal-power normalization when the `buffer` attribute is set, or not.

Its default value is `true` in order to achieve a more uniform output level from the convolver, when loaded with diverse impulse responses. If normalize is set to `false`, then the convolution will be rendered with no pre-processing/scaling of the impulse response. Changes to this value do not take effect until the next time the `buffer` attribute is set.

## Syntax

    var audioCtx = new AudioContext();
    var convolver = audioCtx.createConvolver();
    convolver.normalize = false;

### Value

A boolean.

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

    convolver.normalize = false; // must be set before the buffer, to take effect
    convolver.buffer = concertHallBuffer;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-convolvernode-normalize">Web Audio API<br />
<span class="small">The definition of 'normalize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`normalize`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/normalize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/normalize</a>
