# BaseAudioContext

The `BaseAudioContext` interface of the [Web Audio API](web_audio_api) acts as a base definition for online and offline audio-processing graphs, as represented by [`AudioContext`](audiocontext) and [`OfflineAudioContext`](offlineaudiocontext) respectively. You wouldn't use `BaseAudioContext` directly — you'd use its features via one of these two inheriting interfaces.

A `BaseAudioContext` can be a target of events, therefore it implements the [`EventTarget`](eventtarget) interface.

## Properties

[`BaseAudioContext.audioWorklet`](baseaudiocontext/audioworklet) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
Returns the [`AudioWorklet`](audioworklet) object, which can be used to create and manage [`AudioNode`](audionode)s in which JavaScript code implementing the [`AudioWorkletProcessor`](audioworkletprocessor) interface are run in the background to process audio data.

[`BaseAudioContext.currentTime`](baseaudiocontext/currenttime) <span class="badge inline readonly">Read only </span>  
Returns a double representing an ever-increasing hardware time in seconds used for scheduling. It starts at `0`.

[`BaseAudioContext.destination`](baseaudiocontext/destination) <span class="badge inline readonly">Read only </span>  
Returns an [`AudioDestinationNode`](audiodestinationnode) representing the final destination of all audio in the context. It can be thought of as the audio-rendering device.

[`BaseAudioContext.listener`](baseaudiocontext/listener) <span class="badge inline readonly">Read only </span>  
Returns the [`AudioListener`](audiolistener) object, used for 3D spatialization.

[`BaseAudioContext.sampleRate`](baseaudiocontext/samplerate) <span class="badge inline readonly">Read only </span>  
Returns a float representing the sample rate (in samples per second) used by all nodes in this context. The sample-rate of an [`AudioContext`](audiocontext) cannot be changed.

[`BaseAudioContext.state`](baseaudiocontext/state) <span class="badge inline readonly">Read only </span>  
Returns the current state of the `AudioContext`.

### Event handlers

[`BaseAudioContext.onstatechange`](baseaudiocontext/onstatechange)  
An event handler that runs when an event of type `statechange` has fired. This occurs when the `AudioContext`'s state changes, due to the calling of one of the state change methods ([`AudioContext.suspend`](audiocontext/suspend), [`AudioContext.resume`](audiocontext/resume), or [`AudioContext.close`](audiocontext/close)).

## Methods

_Also implements methods from the interface_ [`EventTarget`](eventtarget).

[`BaseAudioContext.createAnalyser()`](baseaudiocontext/createanalyser)  
Creates an [`AnalyserNode`](analysernode), which can be used to expose audio time and frequency data and for example to create data visualisations.

[`BaseAudioContext.createBiquadFilter()`](baseaudiocontext/createbiquadfilter)  
Creates a [`BiquadFilterNode`](biquadfilternode), which represents a second order filter configurable as several different common filter types: high-pass, low-pass, band-pass, etc

[`BaseAudioContext.createBuffer()`](baseaudiocontext/createbuffer)  
Creates a new, empty [`AudioBuffer`](audiobuffer) object, which can then be populated by data and played via an [`AudioBufferSourceNode`](audiobuffersourcenode).

[`BaseAudioContext.createBufferSource()`](baseaudiocontext/createbuffersource)  
Creates an [`AudioBufferSourceNode`](audiobuffersourcenode), which can be used to play and manipulate audio data contained within an [`AudioBuffer`](audiobuffer) object. [`AudioBuffer`](audiobuffer)s are created using [`AudioContext.createBuffer()`](baseaudiocontext/createbuffer) or returned by [`AudioContext.decodeAudioData()`](baseaudiocontext/decodeaudiodata) when it successfully decodes an audio track.

[`BaseAudioContext.createConstantSource()`](baseaudiocontext/createconstantsource)  
Creates a [`ConstantSourceNode`](constantsourcenode) object, which is an audio source that continuously outputs a monaural (one-channel) sound signal whose samples all have the same value.

[`BaseAudioContext.createChannelMerger()`](baseaudiocontext/createchannelmerger)  
Creates a [`ChannelMergerNode`](channelmergernode), which is used to combine channels from multiple audio streams into a single audio stream.

[`BaseAudioContext.createChannelSplitter()`](baseaudiocontext/createchannelsplitter)  
Creates a [`ChannelSplitterNode`](channelsplitternode), which is used to access the individual channels of an audio stream and process them separately.

[`BaseAudioContext.createConvolver()`](baseaudiocontext/createconvolver)  
Creates a [`ConvolverNode`](convolvernode), which can be used to apply convolution effects to your audio graph, for example a reverberation effect.

[`BaseAudioContext.createDelay()`](baseaudiocontext/createdelay)  
Creates a [`DelayNode`](delaynode), which is used to delay the incoming audio signal by a certain amount. This node is also useful to create feedback loops in a Web Audio API graph.

[`BaseAudioContext.createDynamicsCompressor()`](baseaudiocontext/createdynamicscompressor)  
Creates a [`DynamicsCompressorNode`](dynamicscompressornode), which can be used to apply acoustic compression to an audio signal.

[`BaseAudioContext.createGain()`](baseaudiocontext/creategain)  
Creates a [`GainNode`](gainnode), which can be used to control the overall volume of the audio graph.

[`BaseAudioContext.createIIRFilter()`](baseaudiocontext/createiirfilter)  
Creates an [`IIRFilterNode`](iirfilternode), which represents a second order filter configurable as several different common filter types.

[`BaseAudioContext.createOscillator()`](baseaudiocontext/createoscillator)  
Creates an [`OscillatorNode`](oscillatornode), a source representing a periodic waveform. It basically generates a tone.

[`BaseAudioContext.createPanner()`](baseaudiocontext/createpanner)  
Creates a [`PannerNode`](pannernode), which is used to spatialise an incoming audio stream in 3D space.

[`BaseAudioContext.createPeriodicWave()`](baseaudiocontext/createperiodicwave)  
Creates a [`PeriodicWave`](periodicwave), used to define a periodic waveform that can be used to determine the output of an [`OscillatorNode`](oscillatornode).

[`BaseAudioContext.createScriptProcessor()`](baseaudiocontext/createscriptprocessor) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Creates a [`ScriptProcessorNode`](scriptprocessornode), which can be used for direct audio processing via JavaScript.

[`BaseAudioContext.createStereoPanner()`](baseaudiocontext/createstereopanner)  
Creates a [`StereoPannerNode`](stereopannernode), which can be used to apply stereo panning to an audio source.

[`BaseAudioContext.createWaveShaper()`](baseaudiocontext/createwaveshaper)  
Creates a [`WaveShaperNode`](waveshapernode), which is used to implement non-linear distortion effects.

[`BaseAudioContext.decodeAudioData()`](baseaudiocontext/decodeaudiodata)  
Asynchronously decodes audio file data contained in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). In this case, the ArrayBuffer is usually loaded from an [`XMLHttpRequest`](xmlhttprequest)'s `response` attribute after setting the `responseType` to `arraybuffer`. This method only works on complete files, not fragments of audio files.

## Examples

Basic audio context declaration:

    const audioContext = new AudioContext();

Cross browser variant:

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioContext = new AudioContext();

    const oscillatorNode = audioContext.createOscillator();
    const gainNode = audioContext.createGain();
    const finish = audioContext.destination;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#BaseAudioContext">Web Audio API<br />
<span class="small">The definition of 'BaseAudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`BaseAudioContext`

56

14-56

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

79

12-79

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

53

25-53

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

No

43

15-43

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

14.1

6-14.1

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

56

≤37-56

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

56

18-56

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

53

25-53

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

43

14-43

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

14.5

6-14.5

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

6.0

1.0-6.0

The `BaseAudioContext` interface itself is not present, but many of the methods are available on the [`AudioContext`](https://developer.mozilla.org/docs/Web/API/AudioContext) and [`OfflineAudioContext`](https://developer.mozilla.org/docs/Web/API/OfflineAudioContext) interfaces.

`audioWorklet`

66

79

76

No

Yes

14.1

66

66

79

Yes

14.5

9.0

`createAnalyser`

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

`createBiquadFilter`

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

`createBuffer`

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

`createBufferSource`

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

`createChannelMerger`

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

`createChannelSplitter`

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

`createConstantSource`

56

79

52

No

43

14.1

56

56

52

43

14.5

6.0

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

`createDelay`

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

`createDynamicsCompressor`

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

`createGain`

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

`createIIRFilter`

49

14

50

No

Yes

14.1

49

49

50

Yes

14.5

5.0

`createOscillator`

20

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

`createPanner`

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

`createPeriodicWave`

59

Default values supported

30

12

25

No

17

8

59

Default values supported

≤37

59

Default values supported

30

25

18

8

7.0

Default values supported

2.0

`createScriptProcessor`

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

`createStereoPanner`

42

12

37

No

No

14.1

Yes

Yes

37

No

14.5

Yes

`createWaveShaper`

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

`decodeAudioData`

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

`destination`

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

`listener`

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

`onstatechange`

43

14

40

No

Yes

9

Yes

Yes

40

Yes

9

Yes

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

`state`

43

14

40

No

Yes

9

Yes

Yes

40

Yes

9

Yes

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [`AudioContext`](audiocontext)
- [`OfflineAudioContext`](offlineaudiocontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext</a>
