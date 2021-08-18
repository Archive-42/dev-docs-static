# HTMLMediaElement.currentSrc

The `HTMLMediaElement.currentSrc` property contains the absolute URL of the chosen media resource. This could happen, for example, if the web server selects a media file based on the resolution of the user's display. The value is an empty string if the `networkState` property is `EMPTY`.

## Syntax

    var mediaUrl = audioObject.currentSrc;

### Value

A [`DOMString`](../domstring) object containing the absolute URL of the chosen media source; this may be an empty string if `networkState` is `EMPTY`; otherwise, it will be one of the resources listed by the [`HTMLSourceElement`](../htmlsourceelement) contained within the media element, or the value or src if no [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element is provided.

## Example

    var obj = document.createElement('video');
    console.log(obj.currentSrc); // ""

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-currentsrc">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.currentSrc' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.currentSrc' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`currentSrc`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentSrc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentSrc</a>
