# AudioContext.createMediaElementSource()

The `createMediaElementSource()` method of the [`AudioContext`](../audiocontext) Interface is used to create a new [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) object, given an existing HTML [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, the audio from which can then be played and manipulated.

For more details about media element audio source nodes, check out the [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) reference page.

## Syntax

    var audioCtx = new AudioContext();
    var source = audioCtx.createMediaElementSource(myMediaElement);

### Parameters

`myMediaElement`  
An [`HTMLMediaElement`](../htmlmediaelement) object that you want to feed into an audio processing graph to manipulate.

### Returns

A [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode).

## Example

This simple example creates a source from an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element using `createMediaElementSource()`, then passes the audio through a [`GainNode`](../gainnode) before feeding it into the [`AudioDestinationNode`](../audiodestinationnode) for playback. When the mouse pointer is moved, the `updatePage()` function is invoked, which calculates the current gain as a ratio of mouse Y position divided by overall window height. You can therefore increase and decrease the volume of the playing music by moving the mouse pointer up and down.

**Note**: You can also [view this example running live](https://mdn.github.io/webaudio-examples/media-source-buffer/), or [view the source](https://github.com/mdn/webaudio-examples/tree/master/media-source-buffer).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var myAudio = document.querySelector('audio');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    // Create a MediaElementAudioSourceNode
    // Feed the HTMLMediaElement into it
    var source = audioCtx.createMediaElementSource(myAudio);

    // Create a gain node
    var gainNode = audioCtx.createGain();

    // Create variables to store mouse pointer Y coordinate
    // and HEIGHT of screen
    var CurY;
    var HEIGHT = window.innerHeight;

    // Get new mouse pointer coordinates when mouse is moved
    // then set new gain value

    document.onmousemove = updatePage;

    function updatePage(e) {
        CurY = (window.Event) ? e.pageY : event.clientY + (document.documentElement.scrollTop ? document.documentElement.scrollTop : document.body.scrollTop);

        gainNode.gain.value = CurY/HEIGHT;
    }

    // connect the AudioBufferSourceNode to the gainNode
    // and the gainNode to the destination, so we can play the
    // music and adjust the volume using the mouse cursor
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

**Note**: As a consequence of calling `createMediaElementSource()`, audio playback from the [`HTMLMediaElement`](../htmlmediaelement) will be re-routed into the processing graph of the AudioContext. So playing/pausing the media can still be done through the media element API and the player controls.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-createmediaelementsource">Web Audio API<br />
<span class="small">The definition of 'createMediaElementSource()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createMediaElementSource`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaElementSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/createMediaElementSource</a>
