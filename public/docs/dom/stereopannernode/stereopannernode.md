StereoPannerNode.StereoPannerNode()
===================================

The `StereoPannerNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`StereoPannerNode`](../stereopannernode) object which is an [`AudioNode`](../audionode) that represents a simple stereo panner node that can be used to pan an audio stream left or right.

Syntax
------

    var stereoPannerNode = StereoPannerNode(context, options)

### Parameters

*Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary*.

*context*  
A reference to an [`AudioContext`](../audiocontext).

 *options* <span class="badge inline optional">Optional</span>   
Options are as follows:

-   `pan`: A floating point number in the range \[-1,1\] indicating the position of an [`AudioNode`](../audionode) in an output image. The value -1 represents full left and 1 represents full right. The default value is `0`.

### Return value

A new [`StereoPannerNode`](../stereopannernode) object instance.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-stereopannernode-stereopannernode">Web Audio API<br />
<span class="small">The definition of 'StereoPannerNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StereoPannerNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode/StereoPannerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StereoPannerNode/StereoPannerNode</a>
