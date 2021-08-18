# AudioNode.numberOfInputs

The `numberOfInputs` property of the [`AudioNode`](../audionode) interface returns the number of inputs feeding the node. Source nodes are defined as nodes having a `numberOfInputs` property with a value of 0.

## Syntax

    var numInputs = audioNode.numberOfInputs;

### Value

An integer ≥ 0.

## Example

    const audioCtx = new AudioContext();

    const oscillator = audioCtx.createOscillator();
    const gainNode = audioCtx.createGain();

    oscillator.connect(gainNode).connect(audioCtx.destination);

    console.log(oscillator.numberOfInputs); // 0
    console.log(gainNode.numberOfInputs); // 1
    console.log(audioCtx.destination.numberOfInputs); // 1

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-numberofinputs">Web Audio API<br />
<span class="small">The definition of 'numberOfInputs' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`numberOfInputs`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/numberOfInputs" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/numberOfInputs</a>
