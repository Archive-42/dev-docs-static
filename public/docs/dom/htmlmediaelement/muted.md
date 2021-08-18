# HTMLMediaElement.muted

The `HTMLMediaElement.muted` indicates whether the media element muted.

## Syntax

    var isMuted = audioOrVideo.muted
    audio.muted = true;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). `true` means muted and `false` means not muted.

## Example

    var obj = document.createElement('video');
    console.log(obj.muted); // false

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-muted">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.muted' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.muted' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`muted`

43

12

3.5

9

≤12.1

3.2

Yes

Yes

4

≤12.1

3

Yes

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- [`HTMLMediaElement.defaultMuted`](defaultmuted)
- [`HTMLMediaElement.volume`](volume)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted</a>
