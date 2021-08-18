# AudioNode.numberOfOutputs

The `numberOfOutputs` property of the [`AudioNode`](../audionode) interface returns the number of outputs coming out of the node. Destination nodes — like [`AudioDestinationNode`](../audiodestinationnode) — have a value of 0 for this attribute.

## Syntax

    var numOutputs = audioNode.numberOfOutputs;

### Value

An integer ≥ 0.

## Example

    const audioCtx = new AudioContext();

    const oscillator = audioCtx.createOscillator();
    const gainNode = audioCtx.createGain();

    oscillator.connect(gainNode).connect(audioCtx.destination);

    console.log(oscillator.numberOfOutputs); // 1
    console.log(gainNode.numberOfOutputs); // 1
    console.log(audioCtx.destination.numberOfOutputs); // 0

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-numberofoutputs">Web Audio API<br />
<span class="small">The definition of 'numberOfOutputs' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`numberOfOutputs`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/numberOfOutputs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/numberOfOutputs</a>
