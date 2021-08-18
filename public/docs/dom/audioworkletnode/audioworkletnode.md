# AudioWorkletNode()

The `AudioWorkletNode()` constructor creates a new [`AudioWorkletNode`](../audioworkletnode) object, which represents an [`AudioNode`](../audionode) that uses a JavaScript function to perform custom audio processing.

## Syntax

    var node = new AudioWorkletNode(context, name);
    var node = new AudioWorkletNode(context, name, options);

### Parameters

`context`  
The [`BaseAudioContext`](../baseaudiocontext) instance this node will be associated with.

`name`  
A string, which represents the name of the [`AudioWorkletProcessor`](../audioworkletprocessor) this node will be based on. A processor with the provided name must first be registered using the [`AudioWorkletGlobalScope.registerProcessor()`](../audioworkletglobalscope/registerprocessor) method.

`options` <span class="badge inline optional">Optional</span>  
An object based on the [`AudioWorkletNodeOptions`](../audioworkletnodeoptions) dictionary, which contains zero or more optional properties to configure the new node. The result of [the structured clone algorithm](../web_workers_api/structured_clone_algorithm) applied to the object is also internally passed into the associated [`AudioWorkletProcessor()`](../audioworkletprocessor/audioworkletprocessor) constructor — this allows custom initialization of an underlying user-defined [`AudioWorkletProcessor`](../audioworkletprocessor). Available properties are as follows:

`numberOfInputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfInputs`](../audionode/numberofinputs) property to. Defaults to 1.

`numberOfOutputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfOutputs`](../audionode/numberofoutputs) property to. Defaults to 1.

`outputChannelCount` <span class="badge inline optional">Optional</span>  
An **array** defining the number of channels for each output. For example, _outputChannelCount: \[n, m\]_ specifies the number of channels in the first output to be _n_ and the second output to be _m_. The array length must match `numberOfOutputs`.

`parameterData` <span class="badge inline optional">Optional</span>  
An object containing the initial values of custom [`AudioParam`](../audioparam) objects on this node (in its [`parameters`](parameters) property), with `key` being the name of a custom parameter and `value` being its initial value.

`processorOptions` <span class="badge inline optional">Optional</span>  
Any additional data that can be used for custom initialization of the underlying [`AudioWorkletProcessor`](../audioworkletprocessor).

### Return value

The newly constructed [`AudioWorkletNode`](../audioworkletnode) instance.

### Exceptions

`NotSupportedError`  
The specified `options.outputChannelCount` is `0` or larger than the current implementation supports.

`IndexSizeError`  
The length of `options.outputChannelCount` array does not match `options.numberOfOutputs`.

## Example

_For a complete example demonstrating user-defined audio processing, see the [`AudioWorkletNode`](../audioworkletnode) page._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletnode-audioworkletnode">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioWorkletNode`

66

79

76

No

?

14.1

66

66

79

?

14.5

9.0

## See also

- [Web Audio API](../web_audio_api)
- [Background audio processing using AudioWorklet](../web_audio_api/using_audioworklet)
- [`AudioWorkletNode`](../audioworkletnode) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/AudioWorkletNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/AudioWorkletNode</a>
