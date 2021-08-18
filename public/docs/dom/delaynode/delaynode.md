# DelayNode()

The `DelayNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`DelayNode`](../delaynode) object with a delay-line; an AudioNode audio-processing module that causes a delay between the arrival of an input data, and its propagation to the output.

## Syntax

    var delayNode = new DelayNode(context);
    var delayNode = new DelayNode(context, options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary._

_context_  
A reference to an [`AudioContext`](../audiocontext) or [`OfflineAudioContext`](../offlineaudiocontext).

_options_ <span class="badge inline optional">Optional</span>  
An object specifying the delay node options. Can contain the following members:

- `delayTime`: The initial delay time for the node, in seconds. The default is `0`.
- `maxDelayTime`: The maximum delay time for the node, in seconds. Defaults to `1`.

### Return value

A new [`DelayNode`](../delaynode) object instance.

## Example

    const audioCtx = new AudioContext();
    const delayNode = new DelayNode(audioCtx, {
      delayTime: 0.5,
      maxDelayTime: 2,
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-delaynode-delaynode">Web Audio API<br />
<span class="small">The definition of 'DelayNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DelayNode`

55

Before version 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before version 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DelayNode/DelayNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DelayNode/DelayNode</a>
