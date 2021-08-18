# ConvolverNode()

The `ConvolverNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`ConvolverNode`](../convolvernode) object instance.

## Syntax

    var convolverNode = new ConvolverNode(context, options)

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

_context_  
A reference to an [`AudioContext`](../audiocontext).

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `audioBuffer`: A mono, stereo, or 4-channel _[`AudioBuffer`](../audiobuffer)_ containing the (possibly multichannel) impulse response used by the `ConvolverNode` to create the reverb effect.
- `disableNormalization`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) controlling whether the impulse response from the buffer will be scaled by an equal-power normalization, or not. The default is '`false`'.

### Return value

A new [`ConvolverNode`](../convolvernode) object instance.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>NotSupportedError</code></td><td>The referenced <a href="../audiobuffer"><code>AudioBuffer</code></a> does not have the correct number of channels, or it has a different sample rate to the associated <a href="../audiocontext"><code>AudioContext</code></a>.</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-convolvernode-convolvernode">Web Audio API<br />
<span class="small">The definition of 'ConvolverNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ConvolverNode`

55

79

53

No

42

14.1

55

55

53

42

14.5

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/ConvolverNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode/ConvolverNode</a>
