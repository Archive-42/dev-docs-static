# AudioParamDescriptor

The `AudioParamDescriptor` dictionary of the [Web Audio API](web_audio_api) specifies properties for an [`AudioParam`](audioparam) objects. It is used to create custom `AudioParam`s on an [`AudioWorkletNode`](audioworkletnode). If the underlying [`AudioWorkletProcessor`](audioworkletprocessor) has a [`parameterDescriptors`](audioworkletprocessor/parameterdescriptors) static getter, then the returned array of objects based on this dictionary is used internally by `AudioWorkletNode` constructor to populate its [`parameters`](audioworkletnode/parameters) property accordingly.

## Properties

`name`  
The [`DOMString`](domstring) which represents the name of the `AudioParam`. Under this name the `AudioParam` will be available in the [`parameters`](audioworkletnode/parameters) property of the node, and under this name the [`AudioWorkletProcessor.process`](audioworkletprocessor/process) method will acquire the calculated values of this `AudioParam`.

`automationRate` <span class="badge inline optional">Optional</span>  
Either `"a-rate"`, or `"k-rate"` string which represents an automation rate of this `AudioParam`. Defaults to `"a-rate"`.

`minValue` <span class="badge inline optional">Optional</span>  
A `float` which represents minimum value of the `AudioParam`. Defaults to `-3.4028235e38`.

`maxValue` <span class="badge inline optional">Optional</span>  
A `float` which represents maximum value of the `AudioParam`. Defaults to `3.4028235e38`.

`defaultValue` <span class="badge inline optional">Optional</span>  
A `float` which represents initial value of the `AudioParam`. Defaults to `0`.

## Examples

To demonstrate creation and usage of custom `AudioParam`s, we'll expand the example from [`AudioWorkletNode`](audioworkletnode) page. There we've created a simple node which outputs white noise. Here, additionally, we'll create a custom gain parameter, so we can directly change volume of the output (although you could use [`GainNode`](gainnode) to achieve this as well).

First, we need to define a custom `AudioWorkletProcessor`, and register it. Note that this should be done in a separate file.

We expand the processor by adding a static [`parameterDescriptors`](audioworkletprocessor/parameterdescriptors) getter. It will be used internally by the `AudioWorkletNode` constructor to populate its `parameters` with instantiated `AudioParam` objects.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dictdef-audioparamdescriptor">Web Audio API<br />
<span class="small">The definition of 'AudioParamDescriptor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AudioParamDescriptor`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParamDescriptor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParamDescriptor</a>
