# AudioBufferSourceNode.loop

The `loop` property of the [`AudioBufferSourceNode`](../audiobuffersourcenode) interface is a Boolean indicating if the audio asset must be replayed when the end of the [`AudioBuffer`](../audiobuffer) is reached.

The `loop` property's default value is `false`.

## Syntax

    var loopingEnabled = AudioBufferSourceNode.loop;
    AudioBufferSourceNode.loop = true | false;

### Value

A Boolean which is `true` if looping is enabled; otherwise, the value is `false`.

When looping is enabled, the sound begins playing at the time specified as the start point when [`start()`](start) is called. When the time specified by the [`loopEnd`](loopend) property is reached, playback continues at the time specified by [`loopStart`](loopstart)

## Example

In this example, the [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata) function is used to decode an audio track and put it into an [`AudioBufferSourceNode`](../audiobuffersourcenode). Buttons are provided to play and stop the audio playback, and a slider control is used to change the `playbackRate` property value on the fly. When the audio is played, it loops.

You can [run the full example live](https://mdn.github.io/webaudio-examples/decode-audio-data/) (or [view the source](https://github.com/mdn/webaudio-examples/blob/master/decode-audio-data/index.html).)

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-loop">Web Audio API<br />
<span class="small">The definition of 'loop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`loop`

15

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

- [Web Audio API](../web_audio_api)
- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [`AudioBufferSourceNode`](../audiobuffersourcenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/loop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/loop</a>
