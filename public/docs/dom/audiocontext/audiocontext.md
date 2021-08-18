# AudioContext()

The `AudioContext()` constructor creates a new [`AudioContext`](../audiocontext) object which represents an audio-processing graph, built from audio modules linked together, each represented by an [`AudioNode`](../audionode).

## Syntax

    var audioCtx = new AudioContext();
    var audioCtx = new AudioContext(options);

### Parameters

`options` <span class="badge inline optional">Optional</span>  
An object based on the [`AudioContextOptions`](../audiocontextoptions) dictionary that contains zero or more optional properties to configure the new context. Available properties are as follows:

[`latencyHint`](../audiocontextoptions/latencyhint) <span class="badge inline optional">Optional</span>  
The type of playback that the context will be used for, as a value from the [`AudioContextLatencyCategory`](../audiocontextlatencycategory) enum or a double-precision floating-point value indicating the preferred maximum latency of the context in seconds. The user agent may or may not choose to meet this request; check the value of [`AudioContext.baseLatency`](baselatency) to determine the true latency after creating the context.

[`sampleRate`](../audiocontextoptions/samplerate) <span class="badge inline optional">Optional</span>  
The [`sampleRate`](../baseaudiocontext/samplerate) to be used by the `AudioContext`, specified in samples per second. The value may be any value supported by [`AudioBuffer`](../audiobuffer). If not specified, the preferred sample rate for the context's output device is used by default.

### Return value

The newly constructed [`AudioContext`](../audiocontext) instance.

### Exceptions

`NotSupportedError`  
The specified `sampleRate` isn't supported by the context.

## Usage notes

The specification doesn't go into a lot of detail about things like how many audio contexts a user agent should support, or minimum or maximum latency requirements (if any), so these details can vary from browser to browser. Be sure to check the values if they matter to you.

In particular, the specification doesn't indicate a maximum or minimum number of audio contexts that must be able to be open at the same time, so this is left up to the browser implementations to decide.

### Google Chrome

#### Per-tab audio context limitation in Chrome

Prior to version 66 Google Chrome only supported up to six audio contexts _per tab_ at a time.

#### Non-standard exceptions in Chrome

If the value of the [`latencyHint`](../audiocontextoptions/latencyhint) property isn't valid, Chrome throws a `TypeError` exception with the message "The provided value '...' is not a valid enum value of type AudioContextLatencyCategory".

## Example

This example creates a new [`AudioContext`](../audiocontext) for interactive audio (optimizing for latency) and a sample rate of 44.1kHz.

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext({
      latencyHint: 'interactive',
      sampleRate: 44100,
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-audiocontext">Web Audio API<br />
<span class="small">The definition of 'AudioContext()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`latencyHint`

60

79

No

No

47

No

60

60

No

44

No

8.0

`sampleRate`

74

79

No

No

No

No

74

74

?

?

No

11.0

## See also

- [`new OfflineAudioContext()`](../offlineaudiocontext/offlineaudiocontext) constructor

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/AudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/AudioContext</a>
