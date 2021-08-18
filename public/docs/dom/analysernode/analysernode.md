# AnalyserNode.AnalyserNode()

The `AnalyserNode` constructor of the [Web Audio API](../web_audio_api) creates a new [`AnalyserNode`](../analysernode) object instance.

## Syntax

    var analyserNode = new AnalyserNode(context, ?options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary._

_context_  
A reference to an [`AudioContext`](../audiocontext) or [`OfflineAudioContext`](../offlineaudiocontext).

_options_ <span class="badge inline optional">Optional</span>

- `fftSize`: The desired initial size of the [FFT](https://en.wikipedia.org/wiki/Fast_Fourier_transform) for [frequency-domain](https://en.wikipedia.org/wiki/Frequency_domain) analysis.  
  The default is `2048`.
- `maxDecibels`: The desired initial maximum power in [dB](https://en.wikipedia.org/wiki/Decibel) for FFT analysis.  
  The default is `-30`.
- `minDecibels`: The desired initial minimum power in dB for FFT analysis.  
  The default is `-100`.
- `smoothingTimeConstant`: The desired initial smoothing constant for the FFT analysis. The default is `0.8`.

### Return value

A new [`AnalyserNode`](../analysernode) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-analysernode">Web Audio API<br />
<span class="small">The definition of 'AnalyserNode() constructor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AnalyserNode`

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

## See also

- [`BaseAudioContext.createAnalyser()`](../baseaudiocontext/createanalyser), the equivalent factory method

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/AnalyserNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/AnalyserNode</a>
