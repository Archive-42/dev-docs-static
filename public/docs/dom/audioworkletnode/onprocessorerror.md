# AudioWorkletNode.onprocessorerror

The `onprocessorerror` property of the [`AudioWorkletNode`](../audioworkletnode) interface defines an event handler function to be called when the <span class="page-not-created">`processorerror`</span> event fires. This occurs when the underlying [`AudioWorkletProcessor`](../audioworkletprocessor) behind the node throws an exception in its constructor, the [`process`](../audioworkletprocessor/process) method, or any user-defined class method.

Once an exception is thrown, the processor (and thus the node) will output silence throughout its lifetime.

## Syntax

    audioWorkletNode.onprocessorerror = function() { ... };

## Examples

// FILL IN EXAMPLE SNIPPET

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioworkletnode-onprocessorerror">Web Audio API<br />
<span class="small">The definition of 'onprocessorerror' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`onprocessorerror`

67

79

76

No

?

14.1

67

67

79

?

14.5

9.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/onprocessorerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorkletNode/onprocessorerror</a>
