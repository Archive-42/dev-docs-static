# AudioWorkletProcessor.port

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `port` property of the [`AudioWorkletProcessor`](../audioworkletprocessor) interface returns the associated [`MessagePort`](../messageport). It can be used to communicate between the processor and the [`AudioWorkletNode`](../audioworkletnode) to which it belongs.

**Note**: The port at the other end of the channel is available under the [`port`](../audioworkletnode/port) property of the node.

## Syntax

    AudioWorkletProcessorInstance.port;

### Value

The [`MessagePort`](../messageport) object that is connecting the `AudioWorkletProcessor` and the associated `AudioWorkletNode`.

## Examples

To demonstrate bidirectional communication capabilities, we'll create an `AudioWorkletProcessor`, which will output silence and respond to ping requests from its `AudioWorkletNode`.

First, we need to define a custom `AudioWorkletProcessor`, and register it. Note that this should be done in a separate file.

    // ping-pong-processor.js
    class PingPongProcessor extends AudioWorkletProcessor {
      constructor (...args) {
        super(...args)
        this.port.onmessage = (e) => {
          console.log(e.data)
          this.port.postMessage('pong')
        }
      }
      process (inputs, outputs, parameters) {
        return true
      }
    }

    registerProcessor('ping-pong-processor', PingPongProcessor)

Now in our main scripts file we'll load the processor, create an instance of `AudioWorkletNode` passing the name of the processor, and connect the node to an audio graph.

    const audioContext = new AudioContext()
    await audioContext.audioWorklet.addModule('ping-pong-processor.js')
    const pingPongNode = new AudioWorkletNode(audioContext, 'ping-pong-processor')
    // send the message containing 'ping' string
    // to the AudioWorkletProcessor from the AudioWorkletNode every second
    setInterval(() => pingPongNode.port.postMessage('ping'), 1000)
    pingPongNode.port.onmessage = (e) => console.log(e.data)
    pingPongNode.connect(audioContext.destination)

This will output `"ping"` and `"pong"` strings to the console every second.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletprocessor-port">Web Audio API<br />
<span class="small">The definition of 'port' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

- [Web Audio API](../web_audio_api)
- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/port" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletProcessor/port</a>
