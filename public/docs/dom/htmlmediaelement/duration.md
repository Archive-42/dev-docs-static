# HTMLMediaElement.duration

The _read-only_ [`HTMLMediaElement`](../htmlmediaelement) property `duration` indicates the length of the element's media in seconds.

## Syntax

    myDuration = htmlMediaElement.duration

### Value

A double-precision floating-point value indicating the duration of the media in seconds. If no media data is available, the value `NaN` is returned. If the element's media doesn't have a known duration—such as for live media streams—the value of `duration` is `+Infinity`.

## Examples

    var obj = document.createElement('video');
    console.log(obj.duration); // NaN

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-duration">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.duration' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.duration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`duration`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

## See also

- [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
- [`HTMLMediaElement.currentTime`](currenttime): The current playback position of the media
- The [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/duration</a>
