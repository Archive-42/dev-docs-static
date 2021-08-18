# AudioNode.channelInterpretation

The `channelInterpretation` property of the [`AudioNode`](../audionode) interface represents an enumerated value describing the meaning of the channels. This interpretation will define how audio [up-mixing and down-mixing](../web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) will happen.

When the number of channels doesn't match between an input and an output, up- or down-mixing happens according the following rules. This can be somewhat controlled by setting the [`AudioNode.channelInterpretation`](channelinterpretation) property to `speakers` or `discrete`:

Interpretation

Input channels

Output channels

Mixing rules

`speakers`

`1` _(Mono)_

`2` _(Stereo)_

_Up-mix from mono to stereo_.  
The `M` input channel is used for both output channels (`L` and `R`).  
`output.L = input.M output.R = input.M`

`1` _(Mono)_

`4` _(Quad)_

_Up-mix from mono to quad._  
The `M` input channel is used for non-surround output channels (`L` and `R`). Surround output channels (`SL` and `SR`) are silent.  
`output.L = input.M output.R = input.M output.SL = 0 output.SR = 0`

`1` _(Mono)_

`6` _(5.1)_

_Up-mix from mono to 5.1._  
The `M` input channel is used for the center output channel (`C`). All the others (`L`, `R`, `LFE`, `SL`, and `SR`) are silent.  
`output.L = 0 output.R = 0`  
`output.C = input.M output.LFE = 0 output.SL = 0 output.SR = 0`

`2` _(Stereo)_

`1` _(Mono)_

_Down-mix from stereo to mono_.  
Both input channels (`L` and `R`) are equally combined to produce the unique output channel (`M`).  
`output.M = 0.5 * (input.L + input.R)`

`2` _(Stereo)_

`4` _(Quad)_

_Up-mix from stereo to quad._  
The `L` and `R `input channels are used for their non-surround respective output channels (`L` and `R`). Surround output channels (`SL` and `SR`) are silent.  
`output.L = input.L output.R = input.R output.SL = 0 output.SR = 0`

`2` _(Stereo)_

`6` _(5.1)_

_Up-mix from stereo to 5.1._  
The `L` and `R `input channels are used for their non-surround respective output channels (`L` and `R`). Surround output channels (`SL` and `SR`), as well as the center (`C`) and subwoofer (`LFE`) channels, are left silent.  
`output.L = input.L output.R = input.R output.C = 0 output.LFE = 0 output.SL = 0 output.SR = 0`

`4` _(Quad)_

`1` _(Mono)_

_Down-mix from quad to mono_.  
All four input channels (`L`, `R`, `SL`, and `SR`) are equally combined to produce the unique output channel (`M`).  
` output.M = 0.25 * (input.L + input.R + ``input.SL + input.SR``) `

`4` _(Quad)_

`2` _(Stereo)_

_Down-mix from quad to stereo_.  
Both left input channels (`L` and `SL`) are equally combined to produce the unique left output channel (`L`). And similarly, both right input channels (`R` and `SR`) are equally combined to produce the unique right output channel (`R`).  
` output.L = 0.5 * (input.L + input.SL``) `  
` output.R = 0.5 * (input.R + input.SR``) `

`4` _(Quad)_

`6` _(5.1)_

_Up-mix from quad to 5.1._  
The `L`, `R`, `SL`, and `SR` input channels are used for their respective output channels (`L` and `R`). Center (`C`) and subwoofer (`LFE`) channels are left silent.  
`output.L = input.L output.R = input.R output.C = 0 output.LFE = 0 output.SL = input.SL output.SR = input.SR`

`6` _(5.1)_

`1` _(Mono)_

_Down-mix from 5.1 to mono._  
The left (`L` and `SL`), right (`R` and `SR`) and central channels are all mixed together. The surround channels are slightly attenuated and the regular lateral channels are power-compensated to make them count as a single channel by multiplying by `√2/2`. The subwoofer (`LFE`) channel is lost.  
`output.M = 0.7071 * (input.L + input.R) + input.C + 0.5 * (input.SL + input.SR)`

`6` _(5.1)_

`2` _(Stereo)_

_Down-mix from 5.1 to stereo._  
The central channel (`C`) is summed with each lateral surround channel (`SL` or `SR`) and mixed to each lateral channel. As it is mixed down to two channels, it is mixed at a lower power: in each case it is multiplied by `√2/2`. The subwoofer (`LFE`) channel is lost.  
` output.L = input.L + 0.7071 * (input.C + input.SL) output.R = input.R ``+ 0.7071 * (input.C + input.SR) `

`6` _(5.1)_

`4` _(Quad)_

_Down-mix from 5.1 to quad._  
The central (`C`) is mixed with the lateral non-surround channels (`L` and `R`). As it is mixed down to two channels, it is mixed at a lower power: in each case it is multiplied by `√2/2`. The surround channels are passed unchanged. The subwoofer (`LFE`) channel is lost.  
`output.L = input.L + 0.7071 * input.C output.R = input.R + 0.7071 * input.C output.SL = input.SL output.SR = input.SR`

Other, non-standard layouts

Non-standard channel layouts are handled as if `channelInterpretation` is set to `discrete`.  
The specification explicitly allows the future definition of new speaker layouts. This fallback is therefore not future proof as the behavior of the browsers for a specific number of channels may change in the future.

`discrete`

any (`x`)

any (`y`) where `x<y`

_Up-mix discrete channels._  
Fill each output channel with its input counterpart, that is the input channel with the same index. Channels with no corresponding input channels are left silent.

any (`x`)

any (`y`) where `x>y`

_Down-mix discrete channels._  
Fill each output channel with its input counterpart, that is the input channel with the same index. Input channels with no corresponding output channels are dropped.

## Syntax

    var oscillator = audioCtx.createOscillator();
    oscillator.channelInterpretation = 'discrete';

### Value

An enumerated value representing a [channelInterpretation](https://webaudio.github.io/web-audio-api/#idl-def-ChannelInterpretation).

## Example

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    var oscillator = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillator.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    oscillator.channelInterpretation = 'discrete';

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-channelinterpretation">Web Audio API<br />
<span class="small">The definition of 'channelInterpretation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`channelInterpretation`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelInterpretation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelInterpretation</a>
