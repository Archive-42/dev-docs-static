# AudioWorkletGlobalScope.registerProcessor

The `registerProcessor` method of the [`AudioWorkletGlobalScope`](../audioworkletglobalscope) interface registers a class constructor derived from [`AudioWorkletProcessor`](../audioworkletprocessor) interface under a specified _name_.

## Syntax

    AudioWorkletGlobalScope.registerProcessor(name, processorCtor);

### Parameters

`name`  
A string representing the name under which the processor will be registered.

`processorCtor`  
The constructor of a class derived from [`AudioWorkletProcessor`](../audioworkletprocessor).

**Note**: A key-value pair `{ name: constructor }` is saved internally in the [`AudioWorkletGlobalScope`](../audioworkletglobalscope) once the processor is registered. The _name_ is to be referred to when creating an [`AudioWorkletNode`](../audioworkletnode) based on the registered processor. A new processor by the given name is internally created and associated with the new node.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

`NotSupportedError`

- The _name_ is an empty string, or
- a constructor under the given _name_ is already registered. Registering the same name twice is not allowed.

`TypeError`

- The _processorCtor_ is not a callable constructor, or
- the [`parameterDescriptors`](../audioworkletprocessor/parameterdescriptors) property of the constructor exists and doesn't return an array of [`AudioParamDescriptor`](../audioparamdescriptor)-based objects.

## Examples

In this example we create a custom `AudioWorkletNode` that outputs silence.

First, we need to define a custom [`AudioWorkletProcessor`](../audioworkletprocessor) and register it. Note that this should be done in a separate file.

    // test-processor.js
    class TestProcessor extends AudioWorkletProcessor {
      process (inputs, outputs, parameters) {
        return true
      }
    }

    registerProcessor('test-processor', TestProcessor)

Next, in our main script file we'll load the processor, create an instance of `AudioWorkletNode` — passing it the processor name that we used when calling `registerProcessor` — and connect it to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('test-processor.js')
    const node = new AudioWorkletNode(audioContext, 'test-processor')
    node.connect(audioContext.destination)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletglobalscope-registerprocessor">Web Audio API<br />
<span class="small">The definition of 'registerProcessor()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`registerProcessor`

66

79

76

No

53

No

66

66

No

47

No

9.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope/registerProcessor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope/registerProcessor</a>
