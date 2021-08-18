# ChannelSplitterNode.ChannelSplitterNode()

The `ChannelSplitterNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`ChannelSplitterNode`](../channelsplitternode) object instance, representing a node that splits the input into a separate output for each of the source node's audio channels.

## Syntax

    var splitter = new ChannelSpitterNode(context, options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

`context`  
A [`BaseAudioContext`](../baseaudiocontext) representing the audio context you want the node to be associated with.

`options` <span class="badge inline optional">Optional</span>  
A `ChannelSplitterOptions` dictionary object defining the properties you want the `ChannelSplitterNode` to have (It also inherits the options defined in the `AudioNodeOptions` dictionary):

- `numberOfOutputs`: A number defining the number of inputs the [`ChannelSplitterNode`](../channelsplitternode) should have. If not specified, the default value used is 6.

### Return value

A new [`ChannelSplitterNode`](../channelsplitternode) object instance.

## Example

    var ac = new AudioContext();

    var options = {
      numberOfOutputs : 2
    }

    var mySplitter = new ChannelSplitterNode(ac, options);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#channelsplitternode">Web Audio API<br />
<span class="small">The definition of 'ChannelSplitterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ChannelSplitterNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode/ChannelSplitterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChannelSplitterNode/ChannelSplitterNode</a>
