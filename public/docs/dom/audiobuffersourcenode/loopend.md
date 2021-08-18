# AudioBufferSourceNode.loopEnd

The `loopEnd` property of the [`AudioBufferSourceNode`](../audiobuffersourcenode) interface specifies is a floating point number specifying, in seconds, at what offset into playing the [`AudioBuffer`](../audiobuffer) playback should loop back to the time indicated by the [`loopStart`](loopstart) property. This is only used if the [`loop`](loop) property is `true`.

## Syntax

    AudioBufferSourceNode.loopEnd = endOffsetInSeconds;

    var endOffsetInSeconds = AudioBufferSourceNode.loopEnd;

### Value

A floating-point number indicating the offset, in seconds, into the audio buffer at which each loop will loop return to the beginning of the loop (that is, the current play time gets reset to [`AudioBufferSourceNode.loopStart`](loopstart)). This property is only used if the [`loop`](loop) property is `true`.

The default value is 0.

## Example

In this example, the [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata) function is used to decode an audio track and put it into an [`AudioBufferSourceNode`](../audiobuffersourcenode). Buttons are provided to play and stop the audio playback, and slider controls are used to change the `playbackRate`, `loopStart` and `loopEnd` properties on the fly.

When the audio is played to the end, it loops, but you can control how long the loops last by altering `loopStart` and `loopEnd`. For example, if you set their values to 20 and 25, respectively, then begin playback, the sound will play normally until it reaches the 25 second mark. Then the current play position will loop back to the 20 second mark and continue playing until the 25 second mark, ad infinitum (or at least until [`stop()`](../audioscheduledsourcenode/stop) is called).

For a full working example, see [this code running live](https://mdn.github.io/webaudio-examples/decode-audio-data/), or [view the source](https://github.com/mdn/webaudio-examples/tree/master/decode-audio-data).

    function getData() {
      source = audioCtx.createBufferSource();
      request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
            myBuffer = buffer;
            songLength = buffer.duration;
            source.buffer = myBuffer;
            source.playbackRate.value = playbackControl.value;
            source.connect(audioCtx.destination);
            source.loop = true;

            loopstartControl.setAttribute('max', Math.floor(songLength));
            loopendControl.setAttribute('max', Math.floor(songLength));
          },

          function(e){"Error with decoding audio data" + e.err});

      }

      request.send();
    }

      ...

    loopstartControl.oninput = function() {
      source.loopStart = loopstartControl.value;
      loopstartValue.innerHTML = loopstartControl.value;
    }

    loopendControl.oninput = function() {
      source.loopEnd = loopendControl.value;
      loopendValue.innerHTML = loopendControl.value;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-loopend">Web Audio API<br />
<span class="small">The definition of 'loopEnd' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`loopEnd`

24

12

25

No

15

6

≤37

25

25

14

6

1.5

## See also

- [Web Audio API](../web_audio_api)
- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/loopEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/loopEnd</a>
