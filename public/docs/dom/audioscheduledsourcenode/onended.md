# AudioScheduledSourceNode.onended

The `onended` event handler for the `AudioScheduledSourceNode` interface specifies an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be executed when the `ended` event occurs on the node. This event is sent to the node when the concrete interface (such as [`AudioBufferSourceNode`](../audiobuffersourcenode), [`OscillatorNode`](../oscillatornode), or [`ConstantSourceNode`](../constantsourcenode)) determines that it has stopped playing.

The `ended` event is only sent to a node configured to loop automatically when the node is stopped using its [`stop()`](stop) method. This is the case, for example, when using an [`AudioBufferSourceNode`](../audiobuffersourcenode) with its [`loop`](../audiobuffersourcenode/loop) property set to `true`.

## Syntax

    AudioScheduledSourceNode.onended = EventHandler;

### Value

A function which is called by the browser when the `ended` event occurs on the [`AudioScheduledSourceNode`](../audioscheduledsourcenode). The function receives as input a single parameter, which is an object of type [`Event`](../event) describing the event that occurred.

## Examples

In this simple example, an event listener for the `ended` event is set up to enable a "Start" button in the user interface when the node stops playing.

    node.onended = function(event) {
      document.getElementById("startButton").disabled = false;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioscheduledsourcenode-onended">Web Audio API<br />
<span class="small">The definition of 'onended' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- The `ended` event and its type, [`Event`](../event).
- [`AudioScheduledSourceNode`](../audioscheduledsourcenode)
- [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/onended" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/onended</a>
