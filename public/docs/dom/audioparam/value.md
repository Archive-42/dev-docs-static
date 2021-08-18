# AudioParam.value

The [Web Audio API's](../web_audio_api) [`AudioParam`](../audioparam) interface property `value` gets or sets the value of this [`AudioParam`](../audioparam) at the current time. Initially, the value is set to [`AudioParam.defaultValue`](defaultvalue).

Setting `value` has the same effect as calling [`AudioParam.setValueAtTime`](setvalueattime) with the time returned by the `AudioContext`'s [`currentTime`](../baseaudiocontext/currenttime) property..

## Syntax

    var curValue = audioParam.value;
    audioParam.value = newValue;

### Value

A floating-point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the parameter's value as of the current time. This value will be between the values specified by the [`minValue`](minvalue) and [`maxValue`](maxvalue) properties.

## Usage notes

### Value precision and variation

The data type used internally to store `value` is a single-precision (32-bit) floating point number, while JavaScript uses 64-bit double-precision floating point numbers. As a result, the value you read from the `value` property may not always exactly equal what you set it to.

Consider this example:

    const source = new AudioBufferSourceNode(...);
    const rate = 5.3;
    source.playbackRate.value = rate;
    console.log(source.playbackRate.value === rate);

The log output will be `false`, because the playback rate parameter, `rate`, was converted to the 32-bit floating-point number closest to 5.3, which yields 5.300000190734863. One solution is to use the [`Math.fround()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/fround) method, which returns the single-precision value equivalent to the 64-bit JavaScript value specified—when setting `value`, like this:

    const source = new AudioBufferSourceNode(...);
    const rate = Math.fround(5.3);
    source.playbackRate.value = rate;
    console.log(source.playbackRate.value === rate);

In this case, the log output will be `true`.

### Value of a property which is changing over time

The `value` of an `AudioParam` can either be fixed or can vary over time. This is reflected by the `value` getter, which returns the value of the parameter as of the audio rendering engine's most recent **render quantum**, or moment at which audio buffers are processed and updated. In addition to processing audio buffers, each render quantum updates the `value` of each `AudioParam` as needed given the current time and any established time-based parameter value changes.

Upon first creating the parameter, its value is set to its default value, given by [`AudioParam.defaultValue`](defaultvalue). This is the parameter's value at a time of 0.0 seconds, and will remain the parameter's value until the first render quantum in which the value is altered.

During each render quantum, the browser does the following things related to managing the value of a parameter:

- If the `value` setter has been used, the parameter's value is changed to the value given.
- If the current time equals or exceeds the time specified by a previous call to [`setValueAtTime()`](setvalueattime), the `value` is changed to the value passed into `setValueAtTime()`.
- If any gradiated or ramped value changing methods have been called and the current time is within the time range over which the graduated change should occur, the value is updated based on the appropriate algorithm. These ramped or gradiated value-changing methods include [`linearRampToValueAtTime()`](linearramptovalueattime), [`setTargetAtTime()`](settargetattime), and [`setValueCurveAtTime()`](setvaluecurveattime).

Thus, the `value` of a parameter is maintained to accurately reflect the state of the parameter over time.

## Example

This example instantly changes the volume of a [`GainNode`](../gainnode) to 40%.

    const audioCtx = new AudioContext();
    const gainNode = audioCtx.createGain();
    gainNode.gain.value = 0.4;
    //which is identical to:
    gainNode.gain.setValueAtTime(0.4, audioCtx.currentTime);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-value">Web Audio API<br />
<span class="small">The definition of 'value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`value`

14

12

25

Prior to Firefox 69, `value` did not take into account scheduled or gradiated changes to the parameter's value; instead, only explicitly set values were returned.

No

15

6

≤37

18

25

Firefox for Android does not currently take into account scheduled or gradiated changes to the parameter's value; only the initial value or the most recent explicitly set value is returned.

14

Yes

1.0

When changing the gain value of a [`GainNode`](../gainnode), Google Chrome prior to version 64 (January 2018) would perform a smooth interpolation to prevent dezippering. Starting with version 64, the value is changed instantly to bring it in line with the Web Audio spec. See [Chrome Platform Status](https://www.chromestatus.com/feature/5287995770929152) for details.

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/value</a>
