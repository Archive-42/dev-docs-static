# AudioParam.maxValue

The `maxValue` read-only property of the [`AudioParam`](../audioparam) interface represents the maximum possible value for the parameter's nominal (effective) range.

## Syntax

    var maxVal = audioParam.maxValue;

### Value

A floating-point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the maximum value permitted for the parameter's nominal range.

The default value of `maxValue` is the maximum positive single-precision floating-point value (+340,282,346,638,528,859,811,704,183,484,516,925,440).

## Example

    const audioCtx = new AudioContext();
    const gainNode = audioCtx.createGain();
    console.log(gainNode.gain.maxValue); // 3.4028234663852886e38

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-maxvalue">Web Audio API<br />
<span class="small">The definition of 'maxValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`maxValue`

52

79

53

No

39

6

52

52

53

41

Yes

6.0

## See also

- [`AudioParam.minValue`](minvalue)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/maxValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/maxValue</a>
