# ChannelMergerNode()

The `ChannelMergerNode()` constructor creates a new [`ChannelMergerNode`](../channelmergernode) object instance.

## Syntax

    var myNode = new ChannelMergerNode(context, options);

### Parameters

_context_  
A [`BaseAudioContext`](../baseaudiocontext) representing the audio context you want the node to be associated with.

_options_ <span class="badge inline optional">Optional</span>  
A `ChannelMergerOptions` dictionary object defining the properties you want the `ChannelMergerNode` to have (also inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary):

- `numberOfInputs`: A number defining the number of inputs the [`ChannelMergerNode`](../channelmergernode) should have. If not specified, the default value used is 6.

### Return value

A new [`ChannelMergerNode`](../channelmergernode) object instance.

### Exceptions

`InvalidStateError`  
An option such as `channelCount` or `channelCountMode` has been given an invalid value.

## Example

    var ac = new AudioContext();

    var options = {
      numberOfInputs : 2
    }

    var myMerger = new ChannelMergerNode(ac, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#channelmergernode">Web Audio API<br />
<span class="small">The definition of 'ChannelMergerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ChannelMergerNode`

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

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode/ChannelMergerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChannelMergerNode/ChannelMergerNode</a>
