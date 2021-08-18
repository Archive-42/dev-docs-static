# GainNode()

The `GainNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`GainNode`](../gainnode) object which an [`AudioNode`](../audionode) that represents a change in volume.

**Note**: You should typically call [`BaseAudioContext.createGain`](../baseaudiocontext/creategain) to create a gain node.

## Syntax

    var gainNode = new GainNode(context, options)

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

`context`  
A reference to an [`AudioContext`](../audiocontext).

`options` <span class="badge inline optional">Optional</span>  
Options are as follows:

- `gain`: The amount of gain to apply. This parameter is a-rate and it's nominal range is (-∞,+∞). The default is `1`.

### Return value

A new [`GainNode`](../gainnode) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-gainnode-gainnode">Web Audio API<br />
<span class="small">The definition of 'GainNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`GainNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GainNode/GainNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GainNode/GainNode</a>
