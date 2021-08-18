# AudioContextOptions

The `AudioContextOptions` dictionary is used to specify configuration options when constructing a new [`AudioContext`](audiocontext) object to represent a graph of web audio nodes. It is only used when calling the [`AudioContext()`](audiocontext/audiocontext) constructor.

## Properties

[`latencyHint`](audiocontextoptions/latencyhint) <span class="badge inline optional">Optional</span>  
The type of playback that the context will be used for, as a value from the [`AudioContextLatencyCategory`](audiocontextlatencycategory) enum or a double-precision floating-point value indicating the preferred maximum latency of the context in seconds. The user agent may or may not choose to meet this request; check the value of [`AudioContext.baseLatency`](audiocontext/baselatency) to determine the true latency after creating the context.

[`sampleRate`](audiocontextoptions/samplerate) <span class="badge inline optional">Optional</span>  
The [`sampleRate`](baseaudiocontext/samplerate) to be used by the `AudioContext`, specified in samples per second. The value may be any value supported by [`AudioBuffer`](audiobuffer). If not specified, the preferred sample rate for the context's output device is used by default.

## Constants

### Standard values for latencyHint

The [`latencyHint`](audiocontextoptions/latencyhint) property can be number specifying a preferred maximum latency in seconds or a string from the [`AudioContextLatencyCategory`](audiocontextlatencycategory) enumerated string, which selects a standard value for a given type of audio usage:

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"balanced"</code></td><td>The user agent should balance audio output latency and power consumption when selecting a latency value.</td></tr><tr class="even"><td><code>"interactive"</code></td><td>The audio is involved in interactive elements, such as responding to user actions or needing to coincide with visual cues such as a video or game action. The user agent should select the lowest possible latency that doesn't cause glitches in the audio. This is likely to require increased power consumption. <strong>This is the default value.</strong></td></tr><tr class="odd"><td><code>"playback"</code></td><td>The user agent should select a latency that will maximize playback time by minimizing power consumption at the expense of latency. Useful for non-interactive playback, such as playing music.</td></tr></tbody></table>

## Example

This example instantiates an audio context for music playback (optimized for power consumption over latency), with the sample rate 48,000 Hz.

    let musicContext = new AudioContext({
      latencyHint: "playback",
      sampleRate: 48000
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioContextOptions">Web Audio API<br />
<span class="small">The definition of 'AudioContextOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioContextOptions`

60

≤79

61

No

?

No

60

60

61

?

No

8.0

`latencyHint`

60

≤79

61

No

?

No

60

60

61

?

No

8.0

`sampleRate`

74

79

61

No

No

No

74

74

61

?

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions</a>
