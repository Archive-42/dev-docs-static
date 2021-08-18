# AudioBuffer

The `AudioBuffer` interface represents a short audio asset residing in memory, created from an audio file using the [`AudioContext.decodeAudioData()`](baseaudiocontext/decodeaudiodata) method, or from raw data using [`AudioContext.createBuffer()`](baseaudiocontext/createbuffer). Once put into an AudioBuffer, the audio can then be played by being passed into an [`AudioBufferSourceNode`](audiobuffersourcenode).

Objects of these types are designed to hold small audio snippets, typically less than 45 s. For longer sounds, objects implementing the [`MediaElementAudioSourceNode`](mediaelementaudiosourcenode) are more suitable. The buffer contains data in the following format: non-interleaved IEEE754 32-bit linear PCM with a nominal range between `-1` and `+1`, that is, a 32-bit floating point buffer, with each sample between -1.0 and 1.0. If the [`AudioBuffer`](audiobuffer) has multiple channels, they are stored in separate buffers.

## Constructor

[`AudioBuffer()`](audiobuffer/audiobuffer)  
Creates and returns a new `AudioBuffer` object instance.

## Properties

[`AudioBuffer.sampleRate`](audiobuffer/samplerate) <span class="badge inline readonly">Read only </span>  
Returns a float representing the sample rate, in samples per second, of the PCM data stored in the buffer.

[`AudioBuffer.length`](audiobuffer/length) <span class="badge inline readonly">Read only </span>  
Returns an integer representing the length, in sample-frames, of the PCM data stored in the buffer.

[`AudioBuffer.duration`](audiobuffer/duration) <span class="badge inline readonly">Read only </span>  
Returns a double representing the duration, in seconds, of the PCM data stored in the buffer.

[`AudioBuffer.numberOfChannels`](audiobuffer/numberofchannels) <span class="badge inline readonly">Read only </span>  
Returns an integer representing the number of discrete audio channels described by the PCM data stored in the buffer.

## Methods

[`AudioBuffer.getChannelData()`](audiobuffer/getchanneldata)  
Returns a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing the PCM data associated with the channel, defined by the `channel` parameter (with `0` representing the first channel).

[`AudioBuffer.copyFromChannel()`](audiobuffer/copyfromchannel)  
Copies the samples from the specified channel of the <span class="idlType">`AudioBuffer`</span> to the `destination` array.

[`AudioBuffer.copyToChannel()`](audiobuffer/copytochannel)  
Copies the samples to the specified channel of the <span class="idlType">`AudioBuffer`</span>, from the `source` array.

## Example

The following simple example shows how to create an `AudioBuffer` and fill it with random white noise. You can find the full source code at our [webaudio-examples](https://github.com/mdn/webaudio-examples) repository; a [running live](https://mdn.github.io/webaudio-examples/audio-buffer/) version is also available.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // Create an empty three-second stereo buffer at the sample rate of the AudioContext
    var myArrayBuffer = audioCtx.createBuffer(2, audioCtx.sampleRate * 3, audioCtx.sampleRate);

    // Fill the buffer with white noise;
    // just random values between -1.0 and 1.0
    for (var channel = 0; channel < myArrayBuffer.numberOfChannels; channel++) {
      // This gives us the actual array that contains the data
      var nowBuffering = myArrayBuffer.getChannelData(channel);
      for (var i = 0; i < myArrayBuffer.length; i++) {
        // Math.random() is in [0; 1.0]
        // audio needs to be in [-1.0; 1.0]
        nowBuffering[i] = Math.random() * 2 - 1;
      }
    }

    // Get an AudioBufferSourceNode.
    // This is the AudioNode to use when we want to play an AudioBuffer
    var source = audioCtx.createBufferSource();

    // set the buffer in the AudioBufferSourceNode
    source.buffer = myArrayBuffer;

    // connect the AudioBufferSourceNode to the
    // destination so we can hear the sound
    source.connect(audioCtx.destination);

    // start the source playing
    source.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audiobuffer">Web Audio API<br />
<span class="small">The definition of 'AudioBuffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioBuffer`

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

`AudioBuffer`

55

The `context` parameter was supported up until version 57, but has now been removed.

79

53

No

42

The `context` parameter was supported up until version 44, but has now been removed.

14.1

55

The `context` parameter was supported up until version 57, but has now been removed.

55

The `context` parameter was supported up until version 57, but has now been removed.

53

42

The `context` parameter was supported up until version 44, but has now been removed.

14.5

6.0

The `context` parameter was supported up until Samsung Internet 7.0, but has now been removed.

`copyFromChannel`

43

13

25

No

30

14.1

43

43

25

30

14.5

4.0

`copyToChannel`

43

13

25

No

30

14.1

43

43

25

30

14.5

4.0

`duration`

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

`getChannelData`

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

`length`

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

`numberOfChannels`

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

`sampleRate`

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer</a>
