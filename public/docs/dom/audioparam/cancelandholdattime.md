# AudioParam.cancelAndHoldAtTime()

The `cancelAndHoldAtTime()` property of the [`AudioParam`](../audioparam) interface cancels all scheduled future changes to the `AudioParam` but holds its value at a given time until further changes are made using other methods.

## Syntax

    var audioParam = AudioParam.cancelAndHoldAtTime(cancelTime)

### Parameters

cancelTime  
A double representing the time (in seconds) after the [`AudioContext`](../audiocontext) was first created after which all scheduled changes will be cancelled.

### Return value

A reference to the [`AudioParam`](../audioparam) it was called on.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-cancelandholdattime">Web Audio API<br />
<span class="small">The definition of 'cancelAndHoldAtTime()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancelAndHoldAtTime`

57

79

No

No

44

14.1

57

57

No

43

14.5

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/cancelAndHoldAtTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/cancelAndHoldAtTime</a>
