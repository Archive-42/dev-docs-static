# HTMLImageElement

The `HTMLImageElement` interface represents an HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element, providing the properties and methods used to manipulate image elements.

## Constructor

[`Image()`](htmlimageelement/image)  
The `Image()` constructor creates and returns a new `HTMLImageElement` object representing an HTML [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element which is not attached to any DOM tree. It accepts optional width and height parameters. When called without parameters, ` new ``Image() ` is equivalent to calling [`document.createElement("img")`](document/createelement).

## Properties

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLImageElement.alt`](htmlimageelement/alt)  
A [`DOMString`](domstring) that reflects the [`alt`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-alt) HTML attribute, thus indicating the alternate fallback content to be displayed if the image has not been loaded.

[`HTMLImageElement.complete`](htmlimageelement/complete) <span class="badge inline readonly">Read only </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the browser has finished fetching the image, whether successful or not. That means this value is also `true` if the image has no [`src`](htmlimageelement/src) value indicating an image to load.

[`HTMLImageElement.crossOrigin`](htmlimageelement/crossorigin)  
A [`DOMString`](domstring) specifying the CORS setting for this image element. See [CORS settings attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for further details. This may be `null` if CORS is not used.

[`HTMLImageElement.currentSrc`](htmlimageelement/currentsrc) <span class="badge inline readonly">Read only </span>  
Returns a [`USVString`](usvstring) representing the URL from which the currently displayed image was loaded. This may change as the image is adjusted due to changing conditions, as directed by any [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) which are in place.

[`HTMLImageElement.decoding`](htmlimageelement/decoding)  
An optional [`DOMString`](domstring) representing a hint given to the browser on how it should decode the image. If this value is provided, it must be one of the possible permitted values: `sync` to decode the image synchronously, `async` to decode it asynchronously, or `auto` to indicate no preference (which is the default). Read the [`decoding`](htmlimageelement/decoding) page for details on the implications of this property's values.

[`HTMLImageElement.height`](htmlimageelement/height)  
An integer value that reflects the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-height) HTML attribute, indicating the rendered height of the image in CSS pixels.

[`HTMLImageElement.isMap`](htmlimageelement/ismap)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that reflects the [`ismap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-ismap) HTML attribute, indicating that the image is part of a server-side image map. This is different from a client-side image map, specified using an `<img>` element and a corresponding [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) which contains [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements indicating the clickable areas in the image. The image _must_ be contained within an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element; see the `ismap` page for details.

[`HTMLImageElement.loading`](htmlimageelement/loading)  
A [`DOMString`](domstring) providing a hint to the browser used to optimize loading the document by determining whether to load the image immediately (`eager`) or on an as-needed basis (`lazy`).

[`HTMLImageElement.naturalHeight`](htmlimageelement/naturalheight) <span class="badge inline readonly">Read only </span>  
Returns an integer value representing the intrinsic height of the image in CSS pixels, if it is available; else, it shows `0`. This is the height the image would be if it were rendered at its natural full size.

[`HTMLImageElement.naturalWidth`](htmlimageelement/naturalwidth) <span class="badge inline readonly">Read only </span>  
An integer value representing the intrinsic width of the image in CSS pixels, if it is available; otherwise, it will show `0`. This is the width the image would be if it were rendered at its natural full size.

[`HTMLImageElement.referrerPolicy`](htmlimageelement/referrerpolicy)  
A [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-referrerpolicy) HTML attribute, which tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) how to decide which referrer to use in order to fetch the image. Read this article for details on the possible values of this string.

[`HTMLImageElement.sizes`](htmlimageelement/sizes)  
A [`DOMString`](domstring) reflecting the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) HTML attribute. This string specifies a list of comma-separated conditional sizes for the image; that is, for a given viewport size, a particular image size is to be used. Read the documentation on the [`sizes`](htmlimageelement/sizes) page for details on the format of this string.

[`HTMLImageElement.src`](htmlimageelement/src)  
A [`USVString`](usvstring) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) HTML attribute, which contains the full URL of the image including base URI. You can load a different image into the element by changing the URL in the `src` attribute.

[`HTMLImageElement.srcset`](htmlimageelement/srcset)  
A [`USVString`](usvstring) reflecting the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset) HTML attribute. This specifies a list of candidate images, separated by commas (`',', U+002C COMMA`). Each candidate image is a URL followed by a space, followed by a specially-formatted string indicating the size of the image. The size may be specified either the width or a size multiple. Read the [`srcset`](htmlimageelement/srcset) page for specifics on the format of the size substring.

[`HTMLImageElement.useMap`](htmlimageelement/usemap)  
A [`DOMString`](domstring) reflecting the [`usemap`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-usemap) HTML attribute, containing the page-local URL of the [`<map>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map) element describing the image map to use. The page-local URL is a pound (hash) symbol (`#`) followed by the ID of the `<map>` element, such as `#my-map-element`. The `<map>` in turn contains [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) elements indicating the clickable areas in the image.

[`HTMLImageElement.width`](htmlimageelement/width)  
An integer value that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-width) HTML attribute, indicating the rendered width of the image in CSS pixels.

[`HTMLImageElement.x`](htmlimageelement/x) <span class="badge inline readonly">Read only </span>  
An integer indicating the horizontal offset of the left border edge of the image's CSS layout box relative to the origin of the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element's containing block.

[`HTMLImageElement.y`](htmlimageelement/y) <span class="badge inline readonly">Read only </span>  
The integer vertical offset of the top border edge of the image's CSS layout box relative to the origin of the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element's containing block.

## Obsolete properties

[`HTMLImageElement.align`](htmlimageelement/align) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) indicating the alignment of the image with respect to the surrounding context. The possible values are `"left"`, `"right"`, `"justify"`, and `"center"`. This is obsolete; you should instead use CSS (such as [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align), which works with images despite its name) to specify the alignment.

[`HTMLImageElement.border`](htmlimageelement/border) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) which defines the width of the border surrounding the image. This is deprecated; use the CSS [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property instead.

[`HTMLImageElement.hspace`](htmlimageelement/hspace) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
An integer value which specifies the amount of space (in pixels) to leave empty on the left and right sides of the image.

[`HTMLImageElement.longDesc`](htmlimageelement/longdesc) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`USVString`](usvstring) specifying the URL at which a long description of the image's contents may be found. This is used to turn the image into a hyperlink automatically. Modern HTML should instead place an `<img>` inside an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element defining the hyperlink.

[`HTMLImageElement.lowsrc`](htmlimageelement/lowsrc) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`USVString`](usvstring) specifying the URL of a low-quality (but faster to load) version of the same image. This was once used by browsers under constrained network conditions or on slow devices.

[`HTMLImageElement.name`](htmlimageelement/name) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`DOMString`](domstring) representing the name of the element.

[`HTMLImageElement.vspace`](htmlimageelement/vspace) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
An integer value specifying the amount of empty space, in pixels, to leave above and below the image.

## Methods

_Inherits properties from its parent, [`HTMLElement`](htmlelement)._

[`HTMLImageElement.decode()`](htmlimageelement/decode)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves when the image is decoded and it's safe to append the image to the DOM. This prevents rendering of the next frame from having to pause to decode the image, as would happen if an undecoded image were added to the DOM.

## Errors

If an error occurs while trying to load or render the image, and an [`onerror`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-onerror) event handler has been configured to handle the `error` event, that event handler will get called. This can happen in a number of situations, including:

- The [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) attribute is empty or `null`.
- The specified `src` URL is the same as the URL of the page the user is currently on.
- The specified image is corrupted in some way that prevents it from being loaded.
- The specified image's metadata is corrupted in such a way that it's impossible to retrieve its dimensions, and no dimensions were specified in the `<img>` element's attributes.
- The specified image is in a format not supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

## Example

    var img1 = new Image(); // Image constructor
    img1.src = 'image1.png';
    img1.alt = 'alt';
    document.body.appendChild(img1);

    var img2 = document.createElement('img'); // Use DOM HTMLImageElement
    img2.src = 'image2.jpg';
    img2.alt = 'alt text';
    document.body.appendChild(img2);

    // using first image in the document
    alert(document.images[0].src);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-htmlimageelement-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Extensions to HTMLImageElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>x</code> and <code>y</code> properties.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#htmlimageelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The following properties have been added: <code>srcset</code>, <code>currentSrc</code> and <code>sizes</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-img-element">HTML5<br />
<span class="small">The definition of 'HTMLImageElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>A constructor (with 2 optional parameters) has been added.<br />
The following properties are now obsolete: <code>name</code>, <code>border</code>, <code>align</code>, <code>hspace</code>, <code>vspace</code>, and <code>longdesc</code>.<br />
The following properties are now <code>unsigned long</code>, instead of <code>long</code>: <code>height</code>, and <code>width</code>.<br />
The following properties have been added: <code>crossorigin</code>, <code>naturalWidth</code>, <code>naturalHeight</code>, and <code>complete</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-17701901">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLImgElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>lowsrc</code> property has been removed.<br />
The following properties are now <code>long</code>, instead of <code>DOMString</code>: <code>height</code>, <code>width</code>, <code>hspace</code>, and <code>vspace</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-17701901">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLImgElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLImageElement`

1

12

1

5.5

8

1

1

18

4

10.1

1

1.0

`Image`

1

12

1

5.5

8

10.1

1

18

4

?

1

1.0

`align`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`alt`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`border`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`complete`

1

12

1

5.5

IE reports `false` for broken images.

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`crossOrigin`

13

12

8

11

≤12.1

6

≤37

Yes

8

≤12.1

6

Yes

`currentSrc`

38

13

38

No

25

9

38

38

38

25

9

3.0

`decode`

64

79

68

No

51

11.1

64

64

68

47

11.3

9.0

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

`error_event`

No

No

51

May also be supported in earlier versions.

No

Yes

Yes

No

No

51

Yes

Yes

No

`height`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`hspace`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`isMap`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`loading`

77

79

75

No

64

No

See [bug 196698](https://webkit.org/b/196698)

77

77

79

55

No

See [bug 196698](https://webkit.org/b/196698)

12.0

`longDesc`

1

12

1

6

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`lowsrc`

1

12

1

6

Yes

3

1

Yes

4

?

2

Yes

`name`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`naturalHeight`

1

12

1

9

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`naturalWidth`

1

12

1

9

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`onerror`

No

12

9

5.5

Yes

1

Yes

No

9

Yes

1

No

`referrerPolicy`

53

79

50

No

40

14

53

53

50

41

14

6.0

`sizes`

38

13

38

No

25

9

38

38

38

25

9

3.0

`src`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`srcset`

34

12

38

No

21

6.1

37

34

38

No

6.1

2.0

`useMap`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`vspace`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`width`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

`x`

1

12

14

1-7

No

≤12.1

3

1

Yes

14

4-7

≤12.1

1

Yes

`y`

1

12

14

1-7

No

≤12.1

3

1

Yes

14

4-7

≤12.1

1

Yes

## See also

- The HTML element implementing this interface: [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement</a>
