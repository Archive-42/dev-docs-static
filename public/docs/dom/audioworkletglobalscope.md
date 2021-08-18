# AudioWorkletGlobalScope

The `AudioWorkletGlobalScope` interface of the [Web Audio API](web_audio_api) represents a global execution context for user-supplied code, which defines custom [`AudioWorkletProcessor`](audioworkletprocessor)-derived classes. Each [`BaseAudioContext`](baseaudiocontext) has a single [`AudioWorklet`](audioworklet) available under the [`audioWorklet`](baseaudiocontext/audioworklet) property, which runs its code in a single `AudioWorkletGlobalScope`.

As the global execution context is shared across the current `BaseAudioContext`, it's possible to define any other variables and perform any actions allowed in worklets — apart from defining `AudioWorkletProcessor`-derived classes.

## Properties

<span class="page-not-created">`currentFrame`</span> <span class="badge inline readonly">Read only </span>  
Returns an integer that represents the ever-increasing current sample-frame of the audio block being processed. It is incremented by 128 (the size of a render quantum) after the processing of each audio block.

<span class="page-not-created">`currentTime`</span> <span class="badge inline readonly">Read only </span>  
Returns a double that represents the ever-increasing context time of the audio block being processed. It is equal to the [`currentTime`](baseaudiocontext/currenttime) property of the [`BaseAudioContext`](baseaudiocontext) the worklet belongs to.

<span class="page-not-created">`sampleRate`</span> <span class="badge inline readonly">Read only </span>  
Returns a float that represents the sample rate of the associated [`BaseAudioContext`](baseaudiocontext).

## Methods

[`registerProcessor()`](audioworkletglobalscope/registerprocessor)  
Registers a class derived from the [`AudioWorkletProcessor`](audioworkletprocessor) interface. The class can then be used by creating an [`AudioWorkletNode`](audioworkletnode), providing its registered name.

## Examples

In this example we output all global properties into the console in the constructor of a custom [`AudioWorkletProcessor`](audioworkletprocessor).

First we need to define the processor, and register it. Note that this should be done in a separate file.

    // test-processor.js
    class TestProcessor extends AudioWorkletProcessor {
      constructor () {
        super()
        // current sample-frame and time at the moment of instantiation
        // to see values change, you can put these two lines in process method
        console.log(currentFrame)
        console.log(currentTime)
      }
      // the process method is required - output silence,
      // which the outputs are already filled with
      process (inputs, outputs, parameters) {
        return true
      }
    }

    // the sample rate is not going to change ever,
    // because it's a read-only property of a BaseAudioContext
    // and is set only during its instantiation
    console.log(sampleRate)

    // you can declare any variables and use them in your processors
    // for example it may be an ArrayBuffer with a wavetable
    const usefulVariable = 42
    console.log(usefulVariable)

    registerProcessor('test-processor', TestProcessor)

Next, in our main scripts file we'll load the processor, create an instance of `AudioWorkletNode` — passing the name of the processor to it — and connect the node to an audio graph. We should see the output of `console.log` calls in the console:

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('test-processor.js')
    const testNode = new AudioWorkletNode(audioContext, 'test-processor')
    testNode.connect(audioContext.destination)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworkletglobalscope">Web Audio API<br />
<span class="small">The definition of 'AudioWorkletGlobalScope' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioWorkletGlobalScope`

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

`currentFrame`

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

`currentTime`

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

`sampleRate`

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

- [Web Audio API](web_audio_api)
- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletGlobalScope</a>
