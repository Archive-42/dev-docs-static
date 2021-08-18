# HTMLMediaElement.volume

The `HTMLMediaElement.volume` property sets the volume at which the media will be played.

## Syntax

    var volume = video.volume; //1

### Value

A double values must fall between 0 and 1, where 0 is effectively muted and 1 is the loudest possible value.

## Example

    var obj = document.createElement('audio');
    console.log(obj.volume); // 1
    obj.volume = 0.75;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-volume">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.volume' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.volume' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`volume`

43

12

3.5

9

≤12.1

3.1

Yes

Yes

4

≤12.1

2

Yes

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- [`HTMLMediaElement.muted`](muted)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volume</a>
