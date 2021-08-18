# AudioNode.channelCountMode

The `channelCountMode` property of the [`AudioNode`](../audionode) interface represents an enumerated value describing the way channels must be matched between the node's inputs and outputs.

The possible values of `channelCountMode` and their meanings are:

<table><thead><tr class="header"><th>Value</th><th>Description</th><th>The following <code>AudioNode</code> children default to this value</th></tr></thead><tbody><tr class="odd"><td><code>max</code></td><td>The number of channels is equal to the maximum number of channels of all connections. In this case, <code>channelCount</code> is ignored and only up-mixing happens.</td><td><a href="../gainnode"><code>GainNode</code></a>, <a href="../delaynode"><code>DelayNode</code></a>, <a href="../scriptprocessornode"><code>ScriptProcessorNode</code></a>, <a href="../channelmergernode"><code>ChannelMergerNode</code></a>, <a href="../biquadfilternode"><code>BiquadFilterNode</code></a>, <a href="../waveshapernode"><code>WaveShaperNode</code></a></td></tr><tr class="even"><td><code>clamped-max</code></td><td>The number of channels is equal to the maximum number of channels of all connections, <em>clamped</em> to the value of <code>channelCount</code>.</td><td><a href="../pannernode"><code>PannerNode</code></a>, <a href="../convolvernode"><code>ConvolverNode</code></a>, <a href="../dynamicscompressornode"><code>DynamicsCompressorNode</code></a></td></tr><tr class="odd"><td><code>explicit</code></td><td>The number of channels is defined by the value of <code>channelCount</code>.</td><td><a href="../audiodestinationnode"><code>AudioDestinationNode</code></a>, <a href="../analysernode"><code>AnalyserNode</code></a>, <a href="../channelsplitternode"><code>ChannelSplitterNode</code></a></td></tr></tbody></table>

In older versions of the spec, the default for a [`ChannelSplitterNode`](../channelsplitternode) was max.

## Syntax

    var oscillator = audioCtx.createOscillator();
    oscillator.channelCountMode = 'explicit';

### Value

A enumerated value representing a [channelCountMode](https://webaudio.github.io/web-audio-api/#idl-def-ChannelCountMode).

## Example

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    var oscillator = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillator.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    oscillator.channelCountMode = 'explicit';

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-channelcountmode">Web Audio API<br />
<span class="small">The definition of 'channelCountMode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`channelCountMode`

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

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCountMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCountMode</a>
