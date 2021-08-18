# ConvolverNode

The `ConvolverNode` interface is an [`AudioNode`](audionode) that performs a Linear Convolution on a given [`AudioBuffer`](audiobuffer), often used to achieve a reverb effect. A `ConvolverNode` always has exactly one input and one output.

**Note**: For more information on the theory behind Linear Convolution, see the [Convolution article on Wikipedia](https://en.wikipedia.org/wiki/Convolution).

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>1</code>, <code>2</code>, or <code>4</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`ConvolverNode()`](convolvernode/convolvernode)  
Creates a new `ConvolverNode` object instance.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

[`ConvolverNode.buffer`](convolvernode/buffer)  
A mono, stereo, or 4-channel _[`AudioBuffer`](audiobuffer)_ containing the (possibly multichannel) impulse response used by the `ConvolverNode` to create the reverb effect.

[`ConvolverNode.normalize`](convolvernode/normalize)  
A boolean that controls whether the impulse response from the buffer will be scaled by an equal-power normalization when the `buffer` attribute is set, or not.

## Methods

_No specific method; inherits methods from its parent, [`AudioNode`](audionode)_.

## ConvolverNode Example

The following example shows basic usage of an AudioContext to create a convolver node.

**Note**: You will need to find an impulse response to complete the example below. See this [Codepen](https://codepen.io/DonKarlssonSan/pen/doVKRE) for an applied example.

    let audioCtx = new window.AudioContext();

    async function createReverb() {
        let convolver = audioCtx.createConvolver();

        // load impulse response from file
        let response     = await fetch("path/to/impulse-response.wav");
        let arraybuffer  = await response.arrayBuffer();
        convolver.buffer = await audioCtx.decodeAudioData(arraybuffer);

        return convolver;
    }

    ...

    let reverb = await createReverb();

    // someOtherAudioNode -> reverb -> destination
    someOtherAudioNode.connect(reverb);
    reverb.connect(audioCtx.destination);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#ConvolverNode">Web Audio API<br />
<span class="small">The definition of 'ConvolverNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`buffer`

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

`normalize`

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

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConvolverNode</a>
