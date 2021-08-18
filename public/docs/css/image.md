# &lt;image&gt;

The `<image>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a two-dimensional image.

## Syntax

The `<image>` data type can be represented with any of the following:

- An image denoted by the [`url()`](<url()>) data type
- A [`<gradient>`](gradient) data type
- A part of the webpage, defined by the [`element()`](<element()>) function
- An image, image fragment or solid patch of color, defined by the [`image()`](<image()>) function
- A blending of two or more images defined by the [`cross-fade()`](<cross-fade()>) function.
- A selection of images chosen based on resolution defined by the [`image-set()`](<image-set()>) function.

## Description

CSS can handle the following kinds of images:

- Images with _intrinsic dimensions_ (a natural size), like a JPEG, PNG, or other [raster format](https://en.wikipedia.org/wiki/Raster_graphics).
- Images with _multiple intrinsic dimensions_, existing in multiple versions inside a single file, like some .ico formats. (In this case, the intrinsic dimensions will be those of the image largest in area and the aspect ratio most similar to the containing box.)
- Images with no intrinsic dimensions but with _an intrinsic aspect ratio_ between its width and height, like an SVG or other [vector format](https://en.wikipedia.org/wiki/Vector_graphics).
- <span id="no_intrinsic">Images with _neither intrinsic dimensions, nor an intrinsic aspect ratio_, like a CSS gradient.</span>

CSS determines an object's _concrete size_ using (1) its _intrinsic dimensions_; (2) its _specified size_, defined by CSS properties like [`width`](width), [`height`](height), or [`background-size`](background-size); and (3) its _default size_, determined by the kind of property the image is used with:

<table><thead><tr class="header"><th>Kind of Object (CSS Property)</th><th>Default object size</th></tr></thead><tbody><tr class="odd"><td><a href="background-image"><code>background-image</code></a></td><td>The size of the element's background positioning area</td></tr><tr class="even"><td><a href="list-style-image"><code>list-style-image</code></a></td><td>The size of a <code>1em</code> character</td></tr><tr class="odd"><td><a href="border-image-source"><code>border-image-source</code></a></td><td>The size of the element's border image area</td></tr><tr class="even"><td><a href="cursor"><code>cursor</code></a></td><td>The browser-defined size matching the usual cursor size on the client's system</td></tr><tr class="odd"><td><a href="mask-image"><code>mask-image</code></a></td><td>?</td></tr><tr class="even"><td><a href="shape-outside"><code>shape-outside</code></a></td><td>?</td></tr><tr class="odd"><td><a href="mask-border-source"><code>mask-border-source</code></a></td><td>?</td></tr><tr class="even"><td><a href="symbols()"><code>symbols()</code></a> for @counter-style</td><td>At risk feature. If supported, the browser-defined size matching the usual cursor size on the client's system</td></tr><tr class="odd"><td><a href="content"><code>content</code></a> for a pseudo-element (<a href="::after"><code>::after</code></a>/<a href="::before"><code>::before</code></a>)</td><td>A 300px × 150px rectangle</td></tr></tbody></table>

The concrete object size is calculated using the following algorithm:

- If the specified size defines _both the width and the height_, these values are used as the concrete object size.
- If the specified size defines _only the width or only the height_, the missing value is determined using the intrinsic ratio, if there is any, the intrinsic dimensions if the specified value matches, or the default object size for that missing value.
- If the specified size defines _neither the width nor the height_, the concrete object size is calculated so that it matches the intrinsic aspect ratio of the image but without exceeding the default object size in any dimension. If the image has no intrinsic aspect ratio, the intrinsic aspect ratio of the object it applies to is used; if this object has none, the missing width or height are taken from the default object size.

**Note:** Not all browsers support every type of image on every property. See the [browser compatibility section](#browser_compatibility) for details.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Examples

### Valid images

    url(test.jpg)               /* A <url>, as long as test.jpg is an actual image */
    linear-gradient(blue, red)  /* A <gradient> */
    element(#realid)            /* A part of the webpage, referenced with the element() function,
                                   if "realid" is an existing ID on the page */
    image(ltr 'arrow.png#xywh=0,0,16,16', red)
                                /* A section 16x16 section of <url>, starting from the top, left of the original
                                   image as long as arrow.png is a supported image, otherwise a solid
                                   red swatch. If language is rtl, the image will be horizontally flipped. */
    cross-fade(20% url(twenty.png), url(eighty.png))
                                /* cross faded images, with twenty being 20% opaque
                                   and eighty being 80% opaque. */
    image-set('test.jpg' 1x, 'test-2x.jpg' 2x)
                                /* a selection of images with varying resolutions */

### Invalid images

    nourl.jpg            /* An image file must be defined using the url() function. */
    url(report.pdf)      /* A file pointed to by the url() function must be an image. */
    element(#fakeid)     /* An element ID must be an existing ID on the page. */
    image(z.jpg#xy=0,0)  /* The spatial fragment must be written in the format of xywh=#,#,#,# */
    image-set('cat.jpg' 1x, 'dog.jpg' 1x) /* every image in an image set must have a different resolutions */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#typedef-image">CSS Images Module Level 4<br />
<span class="small">The definition of '&lt;image&gt;' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <a href="element()"><code>element()</code></a>, <a href="image()"><code>image()</code></a>, <a href="image-set()"><code>image-set()</code></a>, <a href="conic-gradient()"><code>conic-gradient()</code></a>, <a href="repeating-conic-gradient()"><code>repeating-conic-gradient()</code></a>, and <a href="image-resolution"><code>image-resolution</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-images-3/#typedef-image">CSS Images Module Level 3<br />
<span class="small">The definition of '&lt;image&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition. Before this, there was no explicitly defined <code>&lt;image&gt;</code> data type. Images could only be defined using the <code>url()</code> functional notation.</td></tr></tbody></table>

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

`image`

1

12

1

10

2

1

1

18

4

11

1

1.0

`cross-fade`

17

Supports the original dual-image with percentage implementation only.

79

Supports the original dual-image with percentage implementation only.

No

No

15

Supports the original dual-image with percentage implementation only.

10

Supports the original dual-image with percentage implementation only.

5.1

Supports the original dual-image with percentage implementation only.

≤37

Supports the original dual-image with percentage implementation only.

18

Supports the original dual-image with percentage implementation only.

No

14

Supports the original dual-image with percentage implementation only.

9.3

Support for the original dual-image with percentage implementation only.

5

Supports the original dual-image with percentage implementation only.

1.0

Support for the original dual-image with percentage implementation only.

`element`

No

No

57

29-57

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`background`](https://developer.mozilla.org/docs/Web/CSS/background), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image) and [`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4-29

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image) and [`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

No

No

60

29-60

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`background`](https://developer.mozilla.org/docs/Web/CSS/background), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image) and [`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4-29

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image) and [`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

`gradient`

26

10

12

3.6

Gradients are limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image), and [`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

10

12.1

11-15

15

6.1

5.1

≤37

≤37

26

18

4

Gradients are limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image), and [`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

12.1

11-14

14

7

6

1.5

1.0

`image`

No

No

No

\["See [bug 703217](https://bugzil.la/703217).", "The [`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect) function supports fragments as of Firefox 4."\]

No

No

No

No

No

No

The [`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect) function supports fragments as of Firefox 4.

No

No

No

`image-set`

21

79

88

\["The `type()` function is not supported as an argument to `image-set()`. See [bug 1695404](https://bugzil.la/1695404).", "In `cursor` and `content` properties, gradients are not supported as arguments to `image-set()`. See [bug 1696314](https://bugzil.la/1696314)."\]

No

15

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

4.4

25

88

\["The `type()` function is not supported as an argument to `image-set()`. See [bug 1695404](https://bugzil.la/1695404).", "In `cursor` and `content` properties, gradients are not supported as arguments to `image-set()`. See [bug 1696314](https://bugzil.la/1696314)."\]

14

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

1.5

`paint`

65

79

No

No

52

No

65

65

No

47

No

9.2

## See also

- [`<gradient>`](gradient)
- [`element()`](<element()>)
- [`image()`](<image()>)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/image</a>
