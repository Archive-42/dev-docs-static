# AudioScheduledSourceNode: ended event

The `ended` event of the [`AudioScheduledSourceNode`](../audioscheduledsourcenode) interface is fired when the source node has stopped playing.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onended"><code>AudioScheduledSourceNode.onended</code></a></td></tr></tbody></table>

## Usage notes

This event occurs when a [`AudioScheduledSourceNode`](../audioscheduledsourcenode) has stopped playing, either because it's reached a predetermined stop time, the full duration of the audio has been performed, or because the entire buffer has been played.

## Examples

In this simple example, an event listener for the `ended` event is set up to enable a "Start" button in the user interface when the node stops playing:

    node.addEventListener('ended', () => {
      document.getElementById("startButton").disabled = false;
    })

You can also set up the event handler using the [`AudioScheduledSourceNode.onended`](onended) property:

    node.onended = function() {
      document.getElementById("startButton").disabled = false;
    }

For an example of the ended event in use, see our [audio-buffer example on GitHub](https://mdn.github.io/webaudio-examples/audio-buffer/).

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

## Related events

- <span class="zhc-markdown-block--checklist-item--remaining-text"><span class="zhc-markdown-block zhc-markdown-block--html">[audioprocess](../scriptprocessornode/audioprocess_event)</span></span>
- <span class="zhc-markdown-block--checklist-item--remaining-text"><span class="zhc-markdown-block zhc-markdown-block--html">[complete](../offlineaudiocontext/complete_event)</span></span>

## See also

- [`HTMLAudioElement`](../htmlaudioelement)
- [`HTMLVideoElement`](../htmlvideoelement)
- [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
- [`HTMLMediaElement: ended event`](../htmlmediaelement/ended_event)
- [`MediaStreamTrack: ended event`](../mediastreamtrack/ended_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/ended_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioScheduledSourceNode/ended_event</a>
