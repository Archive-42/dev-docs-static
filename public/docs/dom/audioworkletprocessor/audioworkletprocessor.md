# AudioWorkletProcessor()

The `AudioWorkletProcessor()` constructor creates a new [`AudioWorkletProcessor`](../audioworkletprocessor) object, which represents an underlying audio processing mechanism of an [`AudioWorkletNode`](../audioworkletnode).

## Syntax

The `AudioWorkletProcessor` and classes that derive from it cannot be instantiated directly from a user-supplied code. Instead, they are created only internally by the creation of an associated [`AudioWorkletNode`](../audioworkletnode)s.

    var processor = new AudioWorkletProcessor(options);

### Parameters

`options`  
An object that is passed as _options_ parameter to [`AudioWorkletNode constructor`](../audioworkletnode/audioworkletnode) and passed through [the structured clone algorithm](../web_workers_api/structured_clone_algorithm). The object is based on [`AudioWorkletNodeOptions`](../audioworkletnodeoptions) dictionary. Available properties are as follows:

`numberOfInputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfInputs`](../audionode/numberofinputs) property to. Defaults to 1.

`numberOfOutputs` <span class="badge inline optional">Optional</span>  
The value to initialize the [`numberOfOutputs`](../audionode/numberofoutputs) property to. Defaults to 1.

`outputChannelCount` <span class="badge inline optional">Optional</span>  
An **array** defining the number of channels for each output. For example, _outputChannelCount: \[n, m\]_ specifies the number of channels in the first output to be _n_ and the second output to be _m_. The array length must match `numberOfOutputs`.

`parameterData` <span class="badge inline optional">Optional</span>  
An object containing the initial values of custom [`AudioParam`](../audioparam) objects on this node (in its [`parameters`](../audioworkletnode/parameters) property), with `key` being the name of a custom parameter and `value` being its initial value.

`processorOptions` <span class="badge inline optional">Optional</span>  
Any additional data that can be used for custom initialization of the underlying [`AudioWorkletProcessor`](../audioworkletprocessor).

Note that there are default values for the first two properties, so even if there are no _options_ object passed to the [`AudioWorkletNode constructor`](../audioworkletnode/audioworkletnode), the _options_ object passed by the node to the `AudioWorkletProcessor` constructor will exist and at minimum have `numberOfInputs` and `numberOfOutputs`.

### Return value

The newly constructed [`AudioWorkletProcessor`](../audioworkletprocessor) instance.

## Example

In this example we pass custom options to the [`AudioWorkletNode constructor`](../audioworkletnode/audioworkletnode) and observe how a [structured clone](../web_workers_api/structured_clone_algorithm) of them gets passed to our `AudioWorkletProcessor` constructor.

First, we need to define a custom [`AudioWorkletProcessor`](../audioworkletprocessor) and register it. Note that this should be done in a separate file.

    // test-processor.js
    class TestProcessor extends AudioWorkletProcessor {
      constructor (options) {
        super()
        console.log(options.numberOfInputs)
        console.log(options.processorOptions.someUsefulVariable)
      }
      process (inputs, outputs, parameters) {
        return true
      }
    }

    registerProcessor('test-processor', TestProcessor)

Next, in our main script file we'll load the processor, create an instance of `AudioWorkletNode` passing it the name of the processor and _options_ object.

In the _options_ object we pass `processorOptions` with a [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) instance under `someUsefulVariable` key. We don't pass `numberOfInputs` and see how it gets its default value.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('test-processor.js')
    const testNode = new AudioWorkletNode(audioContext, 'test-processor', {
      processorOptions: {
        someUsefulVariable: new Map([[1, 'one'], [2, 'two']])
      }
    })

The console output will be as follows:

    > 1 // AudioWorkletNode options.numberOfInputs set to default
    > Map(2) {1 => "one", 2 => "two"} // A cloned map under someUsefulVariable

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletprocessor-audioworkletprocessor">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletProcessor()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioWorkletProcessor`

64

79

76

No

?

No

64

64

79

?

No

9.0

## See also

- [`AudioWorkletNode`](../audioworkletnode) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/AudioWorkletProcessor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/AudioWorkletProcessor</a>
