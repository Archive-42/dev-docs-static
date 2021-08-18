# HTMLImageElement.decoding

The `decoding` property of the [`HTMLImageElement`](../htmlimageelement) interface represents a hint given to the browser on how it should decode the image.

## Syntax

    refStr = imgElem.decoding;
    imgElem.decoding = refStr;

### Values

A [`DOMString`](../domstring) representing the decoding hint. Possible values are:

- `sync`: Decode the image synchronously for atomic presentation with other content.
- `async`: Decode the image asynchronously to reduce delay in presenting other content.
- `auto`: Default mode, which indicates no preference for the decoding mode. The browser decides what is best for the user.

## Usage notes

The `decoding` property allows you to control whether or not the browser is allowed to try to parallelize loading your image. If doing so would cause problems, you can specify `sync` to disable asynchronous loading. This can be useful when applied to [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) elements, but may be even more so when used for offscreen image objects.

## Examples

    var img = new Image();
    img.decoding = 'sync';
    img.src = 'img/logo.png';

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-img-decoding">HTML Living Standard<br />
<span class="small">The definition of 'decoding' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`decoding`

65

79

63

No

52

11.1

65

65

63

47

11.3

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decoding</a>
