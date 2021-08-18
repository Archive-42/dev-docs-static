# AudioBufferSourceNode.playbackRate

The `playbackRate` property of the [`AudioBufferSourceNode`](../audiobuffersourcenode) interface Is a [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) that defines the speed at which the audio asset will be played.

A value of 1.0 indicates it should play at the same speed as its sampling rate, values less than 1.0 cause the sound to play more slowly, while values greater than 1.0 result in audio playing faster than normal. The default value is `1.0`. When set to another value, the `AudioBufferSourceNode` resamples the audio before sending it to the output.

## Syntax

    AudioBufferSourceNode.playbackRate.value = playbackRateProportion;

### Value

An [`AudioParam`](../audioparam) whose [`value`](../audioparam/value) is a floating-point value indicating the playback rate of the audio as a decimal proportion of the original sampling rate.

Consider a sound buffer containing audio sampled at 44.1 kHz (44,100 samples per second). Let's see what a few values of `playbackRate` do:

- A `playbackRate` of 1.0 plays the audio at full speed, or 44,100 Hz.
- A `playbackRate` of 0.5 plays the audio at half speed, or 22,050 Hz.
- A `playbackRate` of 2.0 doubles the audio's playback rate to 88,200 Hz.

## Example

In this example, the [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata) function is used to decode an audio track, and put it into an [`AudioBufferSourceNode`](../audiobuffersourcenode). Buttons are provided to play and stop the audio playback, and a slider control is used to change the `playbackRate` property value on the fly.

You can [run the example live](https://mdn.github.io/webaudio-examples/decode-audio-data/) (or [view the source](https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data).) Play the song and alter the playback rate for some fun results.

    <input class="playback-rate-control" type="range" min="0.25" max="3" step="0.05" value="1">
    <span class="playback-rate-value">1.0</span>

    function getData() {
      source = audioCtx.createBufferSource();
      request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
            myBuffer = buffer;
            source.buffer = myBuffer;
            source.playbackRate.value = playbackControl.value;
            source.connect(audioCtx.destination);
            source.loop = true;
          },

          function(e){"Error with decoding audio data" + e.err});

      }

      request.send();
    }

    // wire up buttons to stop and play audio, and range slider control

    play.onclick = function() {
      getData();
      source.start(0);
      play.setAttribute('disabled', 'disabled');
      playbackControl.removeAttribute('disabled');
    }

    stop.onclick = function() {
      source.stop(0);
      play.removeAttribute('disabled');
      playbackControl.setAttribute('disabled', 'disabled');
    }

    playbackControl.oninput = function() {
      source.playbackRate.value = playbackControl.value;
      playbackValue.innerHTML = playbackControl.value;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-playbackrate">Web Audio API<br />
<span class="small">The definition of 'playbackRate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`playbackRate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/playbackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/playbackRate</a>
