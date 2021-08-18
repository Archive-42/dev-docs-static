# HTMLMediaElement.src

The `HTMLMediaElement.src` property reflects the value of the HTML media element's `src` attribute, which indicates the URL of a media resource to use in the element.

**Note:** The best way to know the URL of the media resource currently in active use in this element is to look at the value of the [`currentSrc`](currentsrc) attribute, which also takes into account selection of a best or preferred media resource from a list provided in an [`HTMLSourceElement`](../htmlsourceelement) (which represents a [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element).

## Syntax

    var mediaUrl = HTMLMediaElement.src;

### Value

A [`USVString`](../usvstring) object containing the URL of a media resource to use in the element; this property reflects the value of the HTML element's `src` attribute.

## Example

    var obj = document.createElement('video');
    console.log(obj.src); // ""

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-src">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.src' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-media-src">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.src' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`src`

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

2

Yes

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/src</a>
