# AudioWorkletProcessor.process

The `process()` method of an [`AudioWorkletProcessor`](../audioworkletprocessor)-derived class implements the audio processing algorithm for the audio processor worklet. Although the method is not a part of the [`AudioWorkletProcessor`](../audioworkletprocessor) interface, any implementation of `AudioWorkletProcessor` must provide a `process()` method.

The method is called synchronously from the audio rendering thread, once for each block of audio (also known as a rendering quantum) being directed through the processor's corresponding [`AudioWorkletNode`](../audioworkletnode). In other words, every time a new block of audio is ready for your processor to manipulate, your `process()` function is invoked to do so.

**Important:** Currently, audio data blocks are always 128 frames long—that is, they contain 128 32-bit floating-point samples for each of the inputs' channels. However, plans are already in place to revise the specification to allow the size of the audio blocks to be changed depending on circumstances (for example, if the audio hardware or CPU utilization is more efficient with larger block sizes). Therefore, you _must always check the size of the sample array_ rather than assuming a particular size.

This size may even be allowed to change over time, so you mustn't look at just the first block and assume the sample buffers will always be the same size.

## Syntax

    var isActivelyProcessing = audioWorkletProcessor.process(inputs, outputs, parameters);

### Parameters

`inputs`  
An array of _inputs_ connected to the node, each item of which is, in turn, an array of _channels_. Each _channel_ is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing 128 samples. For example, `inputs[n][m][i]` will access _n_-th input, _m_-th channel of that input, and _i_-th sample of that channel.

Each sample value is in range of `[-1 .. 1]`.

The number of _inputs_ and thus the length of that array is fixed at the construction of the node (see [`AudioWorkletNodeOptions`](../audioworkletnodeoptions)). If there is no active node connected to the _n_-th input of the node, `inputs[n]` will be an empty array (zero input channels available).

The number of _channels_ in each input may vary, depending on [`channelCount`](../audionode/channelcount) and [`channelCountMode`](../audionode/channelcountmode) properties.

`outputs`  
An array of _outputs_ that is similar to the `inputs` parameter in structure. It is intended to be filled during the execution of the `process()` method. Each of the output channels is filled with zeros by default — the processor will output silence unless the output arrays are modified.

`parameters`  
An object containing string keys and [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) values. For each custom [`AudioParam`](../audioparam) defined using the [`parameterDescriptors`](parameterdescriptors) getter, the key in the object is a `name` of that [`AudioParam`](../audioparam), and the value is a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array). The values of the array are calculated by taking scheduled automation events into consideration.

If the automation rate of the parameter is `"a-rate"`, the array will contain 128 values — one for each frame in the current audio block. If there's no automation happening during the time represented by the current block, the array may contain a single value that is constant for the entire block, instead of 128 identical values.

If the automation rate is `"k-rate"`, the array will contain a single value, which is to be used for each of 128 frames.

### Return value

A Boolean value indicating whether or not to force the [`AudioWorkletNode`](../audioworkletnode) to remain active even if the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) internal logic would otherwise decide that it's safe to shut down the node.

The returned value lets your processor have influence over the lifetime policy of the [`AudioWorkletProcessor`](../audioworkletprocessor) and the node that owns it. If the combination of the return value and the state of the node causes the browser to decide to stop the node, `process()` will not be called again.

Returning `true` forces the Web Audio API to keep the node alive, while returning `false` allows the browser to terminate the node if it is neither generating new audio data nor receiving data through its inputs that it is processing.

The 3 most common types of audio node are:

1.  A source of output. An [`AudioWorkletProcessor`](../audioworkletprocessor) implementing such a node should return `true` from the `process` method as long as it produces an output. The method should return `false` as soon as it's known that it will no longer produce an output. For example, take the [`AudioBufferSourceNode`](../audiobuffersourcenode) — the processor behind such a node should return `true` from the `process` method while the buffer is playing, and start returning `false` when the buffer playing has ended (there's no way to call `play` on the same [`AudioBufferSourceNode`](../audiobuffersourcenode) again).
2.  A node that transforms its input. A processor implementing such a node should return `false` from the `process` method to allow the presence of active input nodes and references to the node to determine whether it can be garbage-collected. An example of a node with this behavior is the [`GainNode`](../gainnode). As soon as there are no inputs connected and references retained, gain can no longer be applied to anything, so it can be safely garbage-collected.
3.  A node that transforms its input, but has a so-called _tail-time_ — this means that it will produce an output for some time even after its inputs are disconnected or are inactive (producing zero-channels). A processor implementing such a node should return `true` from the `process` method for the period of the _tail-time_, beginning as soon as inputs are found that contain zero-channels. An example of such a node is the [`DelayNode`](../delaynode) — it has a _tail-time_ equal to its [`delayTime`](../delaynode/delaytime) property.

**Note**: An absence of the `return` statement means that the method returns `undefined`, and as this is a falsy value, it is like returning `false`. Omitting an explicit `return` statement may cause hard-to-detect problems for your nodes.

### Exceptions

As the `process()` method is implemented by the user, it can throw anything. If an uncaught error is thrown, the node will emit an [`onprocessorerror`](../audioworkletnode/onprocessorerror) event and will output silence for the rest of its lifetime.

## Examples

In this example we create an `AudioWorkletProcessor` that outputs white noise to its first output. The gain can be controlled by the `customGain` parameter.

    class WhiteNoiseProcessor extends AudioWorkletProcessor {
      process (inputs, outputs, parameters) {
        // take the first output
        const output = outputs[0]
        // fill each channel with random values multiplied by gain
        output.forEach(channel => {
          for (let i = 0; i < channel.length; i++) {
            // generate random value for each sample
            // Math.random range is [0; 1); we need [-1; 1]
            // this won't include exact 1 but is fine for now for simplicity
            channel[i] = (Math.random() * 2 - 1) *
              // the array can contain 1 or 128 values
              // depending on if the automation is present
              // and if the automation rate is k-rate or a-rate
              (parameters['customGain'].length > 1
                ? parameters['customGain'][i]
                : parameters['customGain'][0])
          }
        })
        // as this is a source node which generates its own output,
        // we return true so it won't accidentally get garbage-collected
        // if we don't have any references to it in the main thread
        return true
      }
      // define the customGain parameter used in process method
      static get parameterDescriptors () {
        return [{
          name: 'customGain',
          defaultValue: 1,
          minValue: 0,
          maxValue: 1,
          automationRate: 'a-rate'
        }]
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletprocessor-process">Web Audio API<br />
<span class="small">The definition of 'process()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AudioWorkletProcessor.process`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/process</a>
