DynamicsCompressorNode()
========================

The `DynamicsCompressorNode()` constructor creates a new [`DynamicsCompressorNode`](../dynamicscompressornode) object which provides a compression effect, which lowers the volume of the loudest parts of the signal, in order to help prevent clipping and distortion. That can occur when multiple sounds are played and multiplexed together at once.

Syntax
------

    var dynamicsCompressorNode = new DynamicsCompressorNode(context, options)

### Parameters

*context*  
A reference to an [`AudioContext`](../audiocontext).

 *options* <span class="badge inline optional">Optional</span>   
Options are as follows:

-   `attack`: The amount of time (in seconds) to reduce the gain by 10dB. Its default value is 0.003. This parameter is k-rate. Its nominal range is \[0, 1\].
-   `knee`: A decibel value representing the range above the threshold where the curve smoothly transitions to the "ratio" portion. Its default value is 30. This parameter is k-rate. Its nominal range is \[0, 40\].
-   `ratio`: The amount of dB change in input for a 1 dB change in output. Its default value is 12. This parameter is k-rate. Its nominal range is \[1, 20\].
-   release: The amount of time (in seconds) to increase the gain by 10dB. Its default value is 0.250. This parameter is k-rate. Its nominal range is \[0, 1\].
-   threshold: The decibel value above which the compression will start taking effect. Its default value is -24. This parameter is k-rate. Its nominal range is \[-100, 0\].

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dynamicscompressornode">Web Audio API<br />
<span class="small">The definition of 'DynamicsCompressorNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DynamicsCompressorNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/DynamicsCompressorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DynamicsCompressorNode/DynamicsCompressorNode</a>
