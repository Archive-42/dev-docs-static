# AudioContext

The `AudioContext` interface represents an audio-processing graph built from audio modules linked together, each represented by an [`AudioNode`](audionode). An audio context controls both the creation of the nodes it contains and the execution of the audio processing, or decoding. You need to create an `AudioContext` before you do anything else, as everything happens inside a context. It's recommended to create one AudioContext and reuse it instead of initializing a new one each time, and it's OK to use a single `AudioContext` for several different audio sources and pipeline concurrently.

## Constructor

[`AudioContext()`](audiocontext/audiocontext)  
Creates and returns a new `AudioContext` object.

## Properties

_Also inherits properties from its parent interface, [`BaseAudioContext`](baseaudiocontext)._

[`AudioContext.baseLatency`](audiocontext/baselatency) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the number of seconds of processing latency incurred by the [`AudioContext`](audiocontext) passing the audio from the [`AudioDestinationNode`](audiodestinationnode) to the audio subsystem.

[`AudioContext.outputLatency`](audiocontext/outputlatency) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns an estimation of the output latency of the current audio context.

## Methods

_Also inherits methods from its parent interface, [`BaseAudioContext`](baseaudiocontext)._

[`AudioContext.close()`](audiocontext/close)  
Closes the audio context, releasing any system audio resources that it uses.

[`AudioContext.createMediaElementSource()`](audiocontext/createmediaelementsource)  
Creates a [`MediaElementAudioSourceNode`](mediaelementaudiosourcenode) associated with an [`HTMLMediaElement`](htmlmediaelement). This can be used to play and manipulate audio from [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) or [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) elements.

[`AudioContext.createMediaStreamSource()`](audiocontext/createmediastreamsource)  
Creates a [`MediaStreamAudioSourceNode`](mediastreamaudiosourcenode) associated with a [`MediaStream`](mediastream) representing an audio stream which may come from the local computer microphone or other sources.

[`AudioContext.createMediaStreamDestination()`](audiocontext/createmediastreamdestination)  
Creates a [`MediaStreamAudioDestinationNode`](mediastreamaudiodestinationnode) associated with a [`MediaStream`](mediastream) representing an audio stream which may be stored in a local file or sent to another computer.

[`AudioContext.createMediaStreamTrackSource()`](audiocontext/createmediastreamtracksource)  
Creates a [`MediaStreamTrackAudioSourceNode`](mediastreamtrackaudiosourcenode) associated with a [`MediaStream`](mediastream) representing an media stream track.

[`AudioContext.getOutputTimestamp()`](audiocontext/getoutputtimestamp)  
Returns a new `AudioTimestamp` object containing two audio timestamp values relating to the current audio context.

[`AudioContext.resume()`](audiocontext/resume)  
Resumes the progression of time in an audio context that has previously been suspended/paused.

[`AudioContext.suspend()`](audiocontext/suspend)  
Suspends the progression of time in the audio context, temporarily halting audio hardware access and reducing CPU/battery usage in the process.

## Examples

Basic audio context declaration:

    var audioCtx = new AudioContext();

Cross browser variant:

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var oscillatorNode = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();
    var finish = audioCtx.destination;
    // etc.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioContext">Web Audio API<br />
<span class="small">The definition of 'AudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioContext`

35

14-57

12

25

No

22

15-44

14.1

6-14.1

37

≤37-57

35

18-57

25

22

14-43

14.5

6-14.5

3.0

1.0-7.0

`AudioContext`

35

\["Prior to Chrome 66, each tab is limited to 6 audio contexts in Chrome; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, Chrome throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

14-57

12

25

No

22

\["Prior to Opera 53, each tab is limited to 6 audio contexts in Opera; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, Opera throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

15-44

14.1

6

37

\["Prior to WebView 66, each tab is limited to 6 audio contexts in WebView; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, WebView throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

≤37-57

35

\["Prior to Chrome 66, each tab is limited to 6 audio contexts in Chrome; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, Chrome throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

18-57

25

22

\["Prior to Opera Android 47, each tab is limited to 6 audio contexts in Opera; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, Opera throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

14-43

14.5

6

3.0

\["Prior to Samsung Internet 9.0, each tab is limited to 6 audio contexts in Samsung Internet; attempting to create more will throw a `DOMException`. For details see [Per-tab audio context limitation in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Per-tab_audio_context_limitation_in_Chrome).", "If `latencyHint` isn't valid, Samsung Internet throws a `TypeError` exception. See [Non-standard exceptions in Chrome](https://developer.mozilla.org/docs/Web/API/AudioContext/AudioContext#Non-standard_exceptions_in_Chrome) for details."\]

1.0-7.0

`baseLatency`

58

79

70

No

45

14.1

58

58

No

43

14.5

7.0

`close`

42

14

40

No

Yes

9

43

43

40

Yes

9

4.0

`createMediaElementSource`

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

`createMediaStreamDestination`

14

79

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

`createMediaStreamSource`

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

`createMediaStreamTrackSource`

No

No

68

Firefox 68 implements the updated standard's definition of the "first" audio track; now the first track is the one whose ID comes first lexicographically.

No

No

No

No

No

68

Firefox 68 implements the updated standard's definition of the "first" audio track; now the first track is the one whose ID comes first lexicographically.

No

No

No

`getOutputTimestamp`

57

79

70

No

44

14.1

57

57

No

43

14.5

7.0

`outputLatency`

No

No

70

No

No

No

No

No

No

No

No

No

`resume`

41

14

40

No

Yes

9

41

41

Yes

Yes

9

4.0

`suspend`

43

14

40

No

Yes

9

43

43

40

Yes

9

4.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [`OfflineAudioContext`](offlineaudiocontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext</a>
