# AudioNode.disconnect()

The `disconnect()` method of the [`AudioNode`](../audionode) interface lets you disconnect one or more nodes from the node on which the method is called.

## Syntax

    AudioNode.disconnect();

    AudioNode.disconnect(output);

    AudioNode.disconnect(destination);

    AudioNode.disconnect(destination, output);

    AudioNode.disconnect(destination, output, input);

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Parameters

There are several versions of the `disconnect()` method, which accept different combinations of parameters to control which nodes to disconnect from. If no parameters are provided, all outgoing connections are disconnected.

`destination` <span class="badge inline optional">Optional</span>  
An [`AudioNode`](../audionode) or [`AudioParam`](../audioparam) specifying the node or nodes to disconnect from. If this value is an `AudioNode`, a single node is disconnected from, with any other, optional, parameters (`output` and/or `input`) further limiting which inputs and/or outputs should be disconnected. If this value is an `AudioParam`, then the connection to that `AudioParam` is terminated, and the node's contributions to that computed parameter become 0 going forward once the change takes effect. If no matching connection is found, an `InvalidAccessError` exception is thrown.

`output` <span class="badge inline optional">Optional</span>  
An index describing which output from the current `AudioNode` is to be disconnected. The index numbers are defined according to the number of output channels (see [Audio channels](../web_audio_api/basic_concepts_behind_web_audio_api#audio_channels)). If this parameter is out-of-bound, an `IndexSizeError` exception is thrown.

`input` <span class="badge inline optional">Optional</span>  
An index describing which input into the specified destination `AudioNode` is to be disconnected. The index numbers are defined according to the number of input channels (see [Audio channels](../web_audio_api/basic_concepts_behind_web_audio_api#audio_channels)). If this parameter is out-of-bound, an `IndexSizeError` exception is thrown.

### Exceptions

`IndexSizeError`  
A value specified for `input` or `output` is invalid, referring to a node which doesn't exist or outside the permitted range.

`InvalidAccessError`  
The node on which `disconnect()` was called isn't connected to the specified `destination` node.

## Example

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    var oscillator = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillator.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    gainNode.disconnect();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-disconnect">Web Audio API<br />
<span class="small">The definition of 'disconnect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`disconnect`

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

`destination`

43

≤18

No

No

?

No

43

43

No

?

?

4.0

`input`

43

≤18

No

No

?

No

43

43

No

?

?

4.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/disconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/disconnect</a>
