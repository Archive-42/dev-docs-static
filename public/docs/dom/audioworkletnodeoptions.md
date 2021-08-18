# AudioWorkletNodeOptions

The `AudioWorkletNodeOptions` dictionary of the [Web Audio API](web_audio_api) is used to specify configuration options when constructing a new [`AudioWorkletNode`](audioworkletnode) object for custom audio processing. It is only used when calling the [`AudioWorkletNode()`](audioworkletnode/audioworkletnode) constructor. During internal instantiation of the underlying `AudioWorkletProcessor`, the [structured clone algorithm](web_workers_api/structured_clone_algorithm) is applied to the options object and the result is passed into `AudioWorkletProcessor`'s constructor.

## Properties

`numberOfInputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfInputs`](audionode/numberofinputs) property to. Defaults to 1.

`numberOfOutputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfOutputs`](audionode/numberofoutputs) property to. Defaults to 1.

`outputChannelCount` <span class="badge inline optional">Optional</span>  
An **array** defining the number of channels for each output. For example, _outputChannelCount: \[n, m\]_ specifies the number of channels in the first output to be _n_ and the second output to be _m_. The array length must match `numberOfOutputs`.

`parameterData` <span class="badge inline optional">Optional</span>  
An object containing the initial values of custom [`AudioParam`](audioparam) objects on this node (in its [`parameters`](audioworkletnode/parameters) property), with `key` being the name of a custom parameter and `value` being its initial value.

`processorOptions` <span class="badge inline optional">Optional</span>  
Any additional data that can be used for custom initialization of the underlying [`AudioWorkletProcessor`](audioworkletprocessor).

## Usage notes

When creating an [`AudioWorkletNode`](audioworkletnode), these options can have various effects. If the number of inputs and number of outputs are both set to 0, a `NotSupportedError` will be thrown and the node construction process aborted. If the length of the `outputChannelCount` array doesn't match `numberOfOutputs`, an `IndexSizeError` will be thrown.

If `outputChannelCount` isn't specified, and `numberOfInputs` and `numberOfOutputs` are both 1, the `AudioWorkletNode`'s initial channel count is set to 1. This has the effect of changing the output channel count to dynamically change to the computed number of channels, based on the input's channel count and the current setting of the [`AudioNode`](audionode) property [`channelCountMode`](audionode/channelcountmode).

Otherwise, if `outputChannelCount` is provided _and_ if the values of `numberOfInputs` and `numberOfOutputs` are both 1, the audio worklet node's channel count is set to the value of `outputChannelCount`. Otherwise, the channel count of each channel in the set of output channels is set to match the corresponding value in the `outputChannelCount` array.

## Examples

// FILL IN EXAMPLE SNIPPET

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dictdef-audioworkletnodeoptions">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletNodeOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AudioWorkletNodeOptions`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNodeOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNodeOptions</a>
