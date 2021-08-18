# HTMLSourceElement

The `HTMLSourceElement` interface provides special properties (beyond the regular [`HTMLElement`](htmlelement) object interface it also has available to it by inheritance) for manipulating [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) elements.

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

<span class="page-not-created">`HTMLSourceElement.media`</span>  
Is a [`DOMString`](domstring) reflecting the [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-media) HTML attribute, containing the intended type of the media resource.

<span class="page-not-created">`HTMLSourceElement.sizes`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) representing image sizes between breakpoints

<span class="page-not-created">`HTMLSourceElement.src`</span>  
Is a [`DOMString`](domstring) reflecting the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-src) HTML attribute, containing the URL for the media resource. The <span class="page-not-created">`HTMLSourceElement.src`</span> property has a meaning only when the associated [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element is nested in a media element that is a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) or an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element. It has no meaning and is ignored when it is nested in a [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) element.

**Note**: If the `src` property is updated (along with any siblings), the parent [`HTMLMediaElement`](htmlmediaelement)'s `load` method should be called when done, since `<source>` elements are not re-scanned automatically.

<span class="page-not-created">`HTMLSourceElement.srcset`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is a [`DOMString`](domstring) reflecting the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-srcset) HTML attribute, containing a list of candidate images, separated by a comma (`',', U+002C COMMA`). A candidate image is a URL followed by a `'w'` with the width of the images, or an `'x'` followed by the pixel density.

<span class="page-not-created">`HTMLSourceElement.type`</span>  
Is a [`DOMString`](domstring) reflecting the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source#attr-type) HTML attribute, containing the type of the media resource.

## Methods

_No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlsourceelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSourceElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`HTMLSourceElement`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`keySystem`

Yes

≤18

Yes

No

?

No

Yes

Yes

Yes

?

No

Yes

`media`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`sizes`

36

13

38

No

23

10.1

37

36

38

24

10.3

3.0

`src`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`srcset`

38

13

38

No

25

10.1

38

38

38

25

10.3

3.0

`type`

1

12

3.5

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

## See also

- The HTML element implementing this interface: [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source).
- The HTML DOM APIs of the elements that can contain a [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element: [`HTMLVideoElement`](htmlvideoelement), [`HTMLAudioElement`](htmlaudioelement), [`HTMLPictureElement`](htmlpictureelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement</a>
