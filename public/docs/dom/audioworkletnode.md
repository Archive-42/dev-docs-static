# AudioWorkletNode

Although the interface is available outside [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts), the [`BaseAudioContext.audioWorklet`](baseaudiocontext/audioworklet) property is not, thus custom [`AudioWorkletProcessor`](audioworkletprocessor)s cannot be defined outside them.

The `AudioWorkletNode` interface of the [Web Audio API](web_audio_api) represents a base class for a user-defined [`AudioNode`](audionode), which can be connected to an audio routing graph along with other nodes. It has an associated [`AudioWorkletProcessor`](audioworkletprocessor), which does the actual audio processing in a Web Audio rendering thread.

## Constructor

[`AudioWorkletNode()`](audioworkletnode/audioworkletnode)  
Creates a new instance of an `AudioWorkletNode` object.

## Properties

_Also Inherits properties from its parent, [`AudioNode`](audionode)_.

[`AudioWorkletNode.port`](audioworkletnode/port) <span class="badge inline readonly">Read only </span>  
Returns a [`MessagePort`](messageport) used for bidirectional communication between the node and its associated [`AudioWorkletProcessor`](audioworkletprocessor). The other end is available under the [`port`](audioworkletprocessor/port) property of the processor.

[`AudioWorkletNode.parameters`](audioworkletnode/parameters) <span class="badge inline readonly">Read only </span>  
Returns an [`AudioParamMap`](audioparammap) — a collection of [`AudioParam`](audioparam) objects. They are instantiated during the creation of the underlying `AudioWorkletProcessor`. If the `AudioWorkletProcessor` has a static [`parameterDescriptors`](audioworkletprocessor/parameterdescriptors) getter, the [`AudioParamDescriptor`](audioparamdescriptor) array returned from it is used to create `AudioParam` objects on the `AudioWorkletNode`. With this mechanism it is possible to make your own `AudioParam` objects accessible from your `AudioWorkletNode`. You can then use their values in the associated `AudioWorkletProcessor`.

### Event handlers

[`AudioWorkletNode.onprocessorerror`](audioworkletnode/onprocessorerror)  
Fired when an error is thrown in associated [`AudioWorkletProcessor`](audioworkletprocessor). Once fired, the processor and consequently the node will output silence throughout its lifetime.

## Methods

_Also inherits methods from its parent, [`AudioNode`](audionode)_.

_The `AudioWorkletNode` interface does not define any methods of its own._

## Examples

In this example we create a custom `AudioWorkletNode` that outputs white noise.

First, we need to define a custom [`AudioWorkletProcessor`](audioworkletprocessor), which will output white noise, and register it. Note that this should be done in a separate file.

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

Next, in our main script file we'll load the processor, create an instance of `AudioWorkletNode` passing it the name of the processor, and connect the node to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('white-noise-processor.js')
    const whiteNoiseNode = new AudioWorkletNode(audioContext, 'white-noise-processor')
    whiteNoiseNode.connect(audioContext.destination)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworkletnode">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

Yes

14.1

66

66

79

Yes

14.5

9.0

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

`onprocessorerror`

67

79

76

No

?

14.1

67

67

79

?

14.5

9.0

`parameters`

67

79

76

No

Yes

14.1

67

67

79

Yes

14.5

9.0

`port`

67

79

76

No

Yes

14.1

67

67

79

Yes

14.5

9.0

`processorerror_event`

66

79

76

No

?

No

66

66

79

?

No

9.0

## See also

- [Web Audio API](web_audio_api)
- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode</a>
