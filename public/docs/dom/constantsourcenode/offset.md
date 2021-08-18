# ConstantSourceNode.offset

The read-only `offset` property of the [`ConstantSourceNode`](../constantsourcenode) interface returns a [`AudioParam`](../audioparam) object indicating the numeric [a-rate](../audioparam#a-rate) value which is always returned by the source when asked for the next sample.

While the `AudioParam` named `offset` is read-only, the `value` property within is not. So you can change the value of `offset` by setting the value of `ConstantSourceNode.offset.value`:

    myConstantSourceNode.offset.value = newValue;

## Syntax

    let offsetParameter = ConstantAudioNode.offset;

    let offset = ConstantSourceNode.offset.value;
    ConstantSourceNode.offset.value = newValue;

### Value

An [`AudioParam`](../audioparam) object indicating the [a-rate](../audioparam#a-rate) value returned for every sample by this node. The default value is 1.0.

To access the `offset` parameter's current value, access the parameter's `value` property, as shown in the syntax box above.

## Example

This example shows how to set up a `ConstantSourceNode` so its `offset` is used as the input to a pair of [`GainNode`](../gainnode)s; this snippet is derived from the complete example you can find in [Controlling multiple parameters with ConstantSourcenode](../web_audio_api/controlling_multiple_parameters_with_constantsourcenode).

    gainNode2 = context.createGain();
    gainNode3 = context.createGain();
    gainNode2.gain.value = gainNode3.gain.value = 0.5;

    volumeSliderControl.value = gainNode2.gain.value;

    constantSource = context.createConstantSource();
    constantSource.connect(gainNode2.gain);
    constantSource.connect(gainNode3.gain);

First, the gain nodes are created and configured, and a slider control's value is set to match the gain on the two nodes. Then we create a new [`ConstantSourceNode`](../constantsourcenode) and make it the source for the two gain nodes' [`GainNode.gain`](../gainnode/gain) values. Each of those values is also an [`AudioParam`](../audioparam).

Let's say we have an event handler (for `click` events, in this case) which needs to respond by altering the value of the two gain nodes. With the linkage above in place, that can be done using this simple event handler:

    function handleClickEvent(event) {
      constantSource.offset.value = volumeSliderControl.value;
    }

All this function has to do is fetch the current value of the slider control we're using to control the paired nodes' gains, then store that value into the `ConstantSourceNode`'s `offset` parameter. That's done by changing the contents of its [`AudioParam.value`](../audioparam/value) property. The two gain nodes quickly adopt the new volume level.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-constantsourcenode-offset">Web Audio API<br />
<span class="small">The definition of 'offset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`offset`

56

79

52

No

No

14.1

No

No

52

No

14.5

No

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [`ConstantSourceNode`](../constantsourcenode)
- [`AudioNode`](../audionode)
- [`AudioParam`](../audioparam)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode/offset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConstantSourceNode/offset</a>
