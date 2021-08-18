# AudioContextLatencyCategory

**Draft**

This page is not complete.

The `AudioContextLatencyCategory` type is an enumerated set of strings which are used to select one of a number of default values for acceptable maximum latency of an audio context. By using these strings rather than a numeric value when specifying a latency to a [`AudioContext`](audiocontext), you can allow the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to select an appropriate latency for your use case that makes sense on the device on which your content is being used.

`AudioContextLatencyCategory` can be used when constructing a new `AudioContext` by passing one of these values as the [`latencyHint`](audiocontextoptions/latencyhint) option in the [`AudioContext()`](audiocontext/audiocontext) constructor's options dictionary.

## Values

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>"balanced"</code></td><td>The user agent should balance audio output latency and power consumption when selecting a latency value.</td></tr><tr class="even"><td><code>"interactive"</code></td><td>The audio is involved in interactive elements, such as responding to user actions or needing to coincide with visual cues such as a video or game action. The user agent should select the lowest possible latency that doesn't cause glitches in the audio. This is likely to require increased power consumption. <strong>This is the default value.</strong></td></tr><tr class="odd"><td><code>"playback"</code></td><td>The user agent should select a latency that will maximize playback time by minimizing power consumption at the expense of latency. Useful for non-interactive playback, such as playing music.</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#enumdef-audiocontextlatencycategory">Web Audio API<br />
<span class="small">The definition of 'AudioContextLatencyCategory' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioContextLatencyCategory`

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

Showing compatibility for `latencyHint`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContextLatencyCategory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContextLatencyCategory</a>
