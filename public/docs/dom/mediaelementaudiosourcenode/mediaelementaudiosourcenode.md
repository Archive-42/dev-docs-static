MediaElementAudioSourceNode()
=============================

The `MediaElementAudioSourceNode()` constructor creates a new [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) object instance.

Syntax
------

    var myAudioSource = new MediaElementAudioSourceNode(context, options);

### Parameters

*Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary*.

*context*  
An [`AudioContext`](../audiocontext) representing the audio context you want the node to be associated with.

*options*  
A `MediaElementAudioSourceOptions` dictionary object defining the properties you want the `MediaElementAudioSourceNode` to have:

-   `mediaElement`: An [`HTMLMediaElement`](../htmlmediaelement) that will be used as the source for the audio.

### Return value

A new [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) object instance.

Example
-------

    var ac = new AudioContext();
    var mediaElement = document.createElement('audio');

    var options = {
      mediaElement : mediaElement
    }

    var myAudioSource = new MediaElementAudioSourceNode(ac, options);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediaelementaudiosourcenode">Web Audio API<br />
<span class="small">The definition of 'MediaElementAudioSourceNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`MediaElementAudioSourceNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode/MediaElementAudioSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaElementAudioSourceNode/MediaElementAudioSourceNode</a>
