MediaStreamAudioDestinationNode.MediaStreamAudioDestinationNode()
=================================================================

The `MediaStreamAudioDestinationNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode) object instance.

Syntax
------

    var myAudioDest = new MediaStreamAudioDestinationNode(context, options);

### Parameters

*Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary*.

*context*  
An [`AudioContext`](../audiocontext) representing the audio context you want the node to be associated with.

*options <span class="badge inline optional">Optional</span>*  
An `AudioNodeOptions` dictionary object defining the properties you want the `MediaStreamAudioDestinationNode` to have.

### Return value

A new [`MediaStreamAudioDestinationNode`](../mediastreamaudiodestinationnode) object instance.

Example
-------

    var ac = new AudioContext();

    var myDestination = new MediaStreamAudioDestinationNode(ac);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#mediastreamaudiodestinationnode">Web Audio API<br />
<span class="small">The definition of 'MediaStreamAudioDestinationNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`MediaStreamAudioDestinationNode`

55

Before Chrome 59, the default values were not supported.

≤79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode/MediaStreamAudioDestinationNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamAudioDestinationNode/MediaStreamAudioDestinationNode</a>
