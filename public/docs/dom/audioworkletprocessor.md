# AudioWorkletProcessor

The `AudioWorkletProcessor` interface of the [Web Audio API](web_audio_api) represents an audio processing code behind a custom [`AudioWorkletNode`](audioworkletnode). It lives in the [`AudioWorkletGlobalScope`](audioworkletglobalscope) and runs on the Web Audio rendering thread. In turn, an [`AudioWorkletNode`](audioworkletnode) based on it runs on the main thread.

## Constructor

The `AudioWorkletProcessor` and classes that derive from it cannot be instantiated directly from a user-supplied code. Instead, they are created only internally by the creation of an associated [`AudioWorkletNode`](audioworkletnode)s. The constructor of the deriving class is getting called with an options object, so you can perform a custom initialization procedures — see constructor page for details.

[`AudioWorkletProcessor()`](audioworkletprocessor/audioworkletprocessor)  
Creates a new instance of an `AudioWorkletProcessor` object.

## Properties

[`port`](audioworkletprocessor/port) <span class="badge inline readonly">Read only </span>  
Returns a [`MessagePort`](messageport) used for bidirectional communication between the processor and the [`AudioWorkletNode`](audioworkletnode) which it belongs to. The other end is available under the [`port`](audioworkletnode/port) property of the node.

## Methods

_The `AudioWorkletProcessor` interface does not define any methods of its own. However, you must provide a [`process()`](audioworkletprocessor/process) method, which is called in order to process the audio stream._

## Events

_The `AudioWorkletProcessor` interface doesn't respond to any events._

## Usage notes

### Deriving classes

To define custom audio processing code you have to derive a class from the `AudioWorkletProcessor` interface. Although not defined on the interface, the deriving class must have the [`process`](audioworkletprocessor/process) method. This method gets called for each block of 128 sample-frames and takes input and output arrays and calculated values of custom [`AudioParam`](audioparam)s (if they are defined) as parameters. You can use inputs and audio parameter values to fill the outputs array, which by default holds silence.

Optionally, if you want custom [`AudioParam`](audioparam)s on your node, you can supply a [`parameterDescriptors`](audioworkletprocessor/parameterdescriptors) property as a _static getter_ on the processor. The array of [`AudioParamDescriptor`](audioparamdescriptor)-based objects returned is used internally to create the [`AudioParam`](audioparam)s during the instantiation of the `AudioWorkletNode`.

The resulting `AudioParam`s reside in the [`parameters`](audioworkletnode/parameters) property of the node and can be automated using standard methods such as `linearRampToValueAtTime`. Their calculated values will be passed into the [`process()`](audioworkletprocessor/process) method of the processor for you to shape the node output accordingly.

### Processing audio

An example algorithm of creating a custom audio processing mechanism is:

1.  Create a separate file;
2.  In the file:
    1.  Extend the `AudioWorkletProcessor` class (see ["Deriving classes" section](#deriving_classes)) and supply your own [`process()`](audioworkletprocessor/process) method in it;
    2.  Register the processor using [`AudioWorkletGlobalScope.registerProcessor()`](audioworkletglobalscope/registerprocessor) method;
3.  Load the file using [`addModule()`](worklet/addmodule) method on your audio context's [`audioWorklet`](baseaudiocontext/audioworklet) property;
4.  Create an [`AudioWorkletNode`](audioworkletnode) based on the processor. The processor will be instantiated internally by the `AudioWorkletNode` constructor.
5.  Connect the node to the other nodes.

## Examples

In the example below we create a custom [`AudioWorkletNode`](audioworkletnode) that outputs white noise.

First, we need to define a custom `AudioWorkletProcessor`, which will output white noise, and register it. Note that this should be done in a separate file.

    // white-noise-processor.js
    class WhiteNoiseProcessor extends AudioWorkletProcessor {
      process (inputs, outputs, parameters) {
        const output = outputs[0]
        output.forEach(channel => {
          for (let i = 0; i < channel.length; i++) {
            channel[i] = Math.random() * 2 - 1
          }
        })
        return true
      }
    }

    registerProcessor('white-noise-processor', WhiteNoiseProcessor)

Next, in our main script file we'll load the processor, create an instance of [`AudioWorkletNode`](audioworkletnode), passing it the name of the processor, then connect the node to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('white-noise-processor.js')
    const whiteNoiseNode = new AudioWorkletNode(audioContext, 'white-noise-processor')
    whiteNoiseNode.connect(audioContext.destination)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworkletprocessor">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletProcessor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`port`

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

- [Web Audio API](web_audio_api)
- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor</a>
