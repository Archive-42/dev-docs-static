# HTMLMediaElement.ended

The `HTMLMediaElement.ended` indicates whether the media element has ended playback.

## Syntax

    var isEnded = HTMLMediaElement.ended

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the media contained in the element has finished playing.

If the source of the media is a [`MediaStream`](../mediastream), this value is `true` if the value of the stream's [`active`](../mediastream/active) property is `false`.

## Example

    var obj = document.createElement('video');
    console.log(obj.ended); // false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-ended">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.ended' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.ended' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`ended`

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

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- [`MediaStream`](../mediastream)
- [`MediaStream.active`](../mediastream/active)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/ended</a>
