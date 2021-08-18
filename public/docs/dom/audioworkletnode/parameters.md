# AudioWorkletNode.parameters

The read-only `parameters` property of the [`AudioWorkletNode`](../audioworkletnode) interface returns the associated [`AudioParamMap`](../audioparammap) — that is, a `Map`-like collection of [`AudioParam`](../audioparam) objects. They are instantiated during creation of the underlying [`AudioWorkletProcessor`](../audioworkletprocessor) according to its [`parameterDescriptors`](../audioworkletprocessor/parameterdescriptors) static getter.

## Syntax

    audioWorkletNodeInstance.parameters

### Value

The [`AudioParamMap`](../audioparammap) object containing [`AudioParam`](../audioparam) instances. They can be automated in the same way as with default `AudioNode`s, and their calculated values can be used in the [`process`](../audioworkletprocessor/process) method of your [`AudioWorkletProcessor`](../audioworkletprocessor).

## Examples

To demonstrate creation and usage of custom `AudioParam`s, we'll expand the example from [`AudioWorkletNode`](../audioworkletnode) page. There we've created a simple node which outputs white noise. Here, additionally, we'll create a custom gain parameter, so we can directly change volume of the output (although you could use [`GainNode`](../gainnode) to achieve this as well).

First, we need to define a custom `AudioWorkletProcessor`, and register it. Note that this should be done in a separate file.

We expand the processor by adding a static [`parameterDescriptors`](../audioworkletprocessor/parameterdescriptors) getter. It will be used internally by the `AudioWorkletNode` constructor to populate its `parameters` with instantiated `AudioParam` objects.

    // white-noise-processor.js
    class WhiteNoiseProcessor extends AudioWorkletProcessor {
      static get parameterDescriptors () {
        return [{
          name: 'customGain',
          defaultValue: 1,
          minValue: 0,
          maxValue: 1,
          automationRate: 'a-rate'
        }]
      }

      process (inputs, outputs, parameters) {
        const output = outputs[0]
        output.forEach(channel => {
          for (let i = 0; i < channel.length; i++) {
            channel[i] = (Math.random() * 2 - 1) *
              (parameters['customGain'].length > 1 ? parameters['customGain'][i] : parameters['customGain'][0])
            // note: a parameter contains an array of 128 values (one value for each of 128 samples),
            // however it may contain a single value which is to be used for all 128 samples
            // if no automation is scheduled for the moment.
          }
        })
        return true
      }
    }

    registerProcessor('white-noise-processor', WhiteNoiseProcessor)

Next, in our main scripts file we'll load the processor, create an instance of `AudioWorkletNode` passing it the name of the processor, and connect the node to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('white-noise-processor.js')
    const whiteNoiseNode = new AudioWorkletNode(audioContext, 'white-noise-processor')
    whiteNoiseNode.connect(audioContext.destination)

Now we can change the gain on the node like this:

    const gainParam = whiteNoiseNode.parameters.get('customGain')
    gainParam.setValueAtTime(0, audioContext.currentTime)
    gainParam.linearRampToValueAtTime(0.5, audioContext.currentTime + 0.5)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletnode-parameters">Web Audio API<br />
<span class="small">The definition of 'parameters' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [Web Audio API](../web_audio_api)
- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/parameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/parameters</a>
