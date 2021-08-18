# DynamicsCompressorNode.reduction

The `reduction` read-only property of the [`DynamicsCompressorNode`](../dynamicscompressornode) interface is a float representing the amount of gain reduction currently applied by the compressor to the signal.

Intended for metering purposes, it returns a value in dB, or `0` (no gain reduction) if no signal is fed into the `DynamicsCompressorNode`. The range of this value is between `-20` and `0` (in dB).

## Syntax

    var myReduction = compressorNodeInstance.reduction;

### Value

A float.

## Example

    var audioCtx = new AudioContext();
    var compressor = audioCtx.createDynamicsCompressor();
    var myReduction = compressor.reduction;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-dynamicscompressornode-reduction">Web Audio API<br />
<span class="small">The definition of 'reduction' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`reduction`

14

Before version 52, this was an `AudioParam.`.

12

25

No

15

6

≤37

Before version 52, this was an `AudioParam.`.

18

Before version 52, this was an `AudioParam.`.

25

14

Yes

1.0

Before Samsung Internet 6.0, this was an `AudioParam.`.

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/reduction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/reduction</a>
