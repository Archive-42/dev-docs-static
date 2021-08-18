# AudioContextOptions.latencyHint

The [`AudioContextOptions`](../audiocontextoptions) dictionary (used when instantiating an [`AudioContext`](../audiocontext)) may contain a property named `latencyHint`, which indicates the _preferred_ maximum latency in seconds for the audio context. The value is specified either as a member of the string enum [`AudioContextLatencyCategory`](../audiocontextlatencycategory) or a double-precision value.

## Syntax

    audioContextOptions.latencyHint = "interactive";
    audioContextOptions.latencyHint = 0.2;

    var latencyHint = audioContextOptions.latencyHint;

### Value

The preferred maximum latency for the `AudioContext`. There are two ways this value can be specified.

The best way to specify the preferred latency is to use a value form the string enum [`AudioContextLatencyCategory`](../audiocontextlatencycategory). In fact, the default value of `latencyHint` is `"interactive"` (meaning the browser should try to use the lowest possible and reliable latency it can).

The value can also be specified as a double-precision floating-point value, specifying the preferred maximum latency in seconds. This provides more precise control over the balance between audio latency and device energy usage.

To determine the actual latency of the context after creating it, check the value of the context's [`baseLatency`](../audiocontext/baselatency) property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontextoptions-latencyhint">Web Audio API<br />
<span class="small">The definition of 'AudioContextOptions.latencyHint' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`AudioContext`](../audiocontext): The interface describing an audio context
- [`AudioContext()`](../audiocontext/audiocontext): The audio context constructor, which accepts a [`AudioContextOptions`](../audiocontextoptions) object as an input.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions/latencyHint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions/latencyHint</a>
