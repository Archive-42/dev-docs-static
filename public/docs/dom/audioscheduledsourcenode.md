# AudioScheduledSourceNode

The `AudioScheduledSourceNode` interface—part of the Web Audio API—is a parent interface for several types of audio source node interfaces which share the ability to be started and stopped, optionally at specified times. Specifically, this interface defines the [`start()`](audioscheduledsourcenode/start) and [`stop()`](audioscheduledsourcenode/stop) methods, as well as the [`onended`](audioscheduledsourcenode/onended) event handler.

You can't create an `AudioScheduledSourceNode` object directly. Instead, use the interface which extends it, such as [`AudioBufferSourceNode`](audiobuffersourcenode), [`OscillatorNode`](oscillatornode), and [`ConstantSourceNode`](constantsourcenode).

Unless stated otherwise, nodes based upon `AudioScheduledSourceNode` output silence when not playing (that is, before `start()` is called and after `stop()` is called). Silence is represented, as always, by a stream of samples with the value zero (0).

## Properties

_Inherits properties from its parent interface, [`AudioNode`](audionode)._

## Methods

_Inherits methods from its parent interface, [`AudioNode`](audionode), and adds the following methods:_

[`start()`](audioscheduledsourcenode/start)  
Schedules the node to begin playing the constant sound at the specified time. If no time is specified, the node begins playing immediately.

[`stop()`](audioscheduledsourcenode/stop)  
Schedules the node to stop playing at the specified time. If no time is specified, the node stops playing at once.

## Events

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface:

`ended`  
Fired when the source node has stopped playing, either because it's reached a predetermined stop time, the full duration of the audio has been performed, or because the entire buffer has been played.  
Also available using the `onended` event handler property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioScheduledSourceNode">Web Audio API<br />
<span class="small">The definition of 'AudioScheduledSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioScheduledSourceNode`

57

14-57

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

79

12-79

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

53

25-53

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

No

44

15-44

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

14

6-14

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

57

≤37-57

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

57

18-57

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

53

25-53

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

43

14-43

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

14

6-14

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

7.0

1.0-7.0

The `AudioScheduledSourceNode` interface itself is not present, but some of its members are available on the [`AudioBufferSourceNode`](https://developer.mozilla.org/docs/Web/API/AudioBufferSourceNode), [`ConstantSourceNode`](https://developer.mozilla.org/docs/Web/API/ConstantSourceNode) and [`OscillatorNode`](https://developer.mozilla.org/docs/Web/API/OscillatorNode) interfaces.

`ended_event`

30

12

25

No

17

7

≤37

30

25

18

7

2.0

`onended`

30

12

25

No

17

7

≤37

30

25

18

7

2.0

`start`

24

12

25

No

15

6.1

≤37

25

25

14

7

1.5

`stop`

24

12

25

No

15

6.1

≤37

25

25

14

7

1.5

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)
- [`AudioNode`](audionode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode</a>
