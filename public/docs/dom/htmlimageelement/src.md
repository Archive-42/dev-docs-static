HTMLImageElement.src
====================

The [`HTMLImageElement`](../htmlimageelement) property `src`, which reflects the HTML [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) attribute, specifies the image to display in the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

Syntax
------

    htmlImageElement.src = newSource;
    let src = htmlImageElement.src;

### Value

When providing only a single image, rather than a set of images from which the browser selects the best match for the viewport size and display pixel density, the `src` attribute is a [`USVString`](../usvstring) specifying the URL of the desired image. This can be set either within the HTML itself using the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) content attribute, or programmatically by setting the element's `src` property.

If you use the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset) content attribute to provide multiple image options for different display pixel densities, the URL specified by the `src` attribute is used in one of two ways:

-   as a fallback for browsers that don't support `srcset`.
-   as an equivalent for specifying an image in `srcset` with the size multiplier `1x`; that is, the image specified by `src` is used on low-density screens (such as typical 72 DPI or 96 DPI displays).

Additionally, if you use `src` along with *both* [`sizes`](sizes) (or the corresponding [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) content attribute) *and* `srcset` in order to choose an image based on the viewport size, the `src` attribute is only used as a fallback for browsers that don't support `sizes` and `srcset`; otherwise, it's not used at all.

Examples
--------

### Specifying a single image

#### HTML

    <img src="https://interactive-examples.mdn.mozilla.net/media/examples/grapefruit-slice-332-332.jpg"
         width="160"
         alt="Slices of grapefruit, looking yummy.">

#### Result

### Using src with an image set

When using a set of images with the [`srcset`](srcset) property, the `src` serves as either a fallback for older browsers, or as the `1x` size of the image.

#### HTML

#### Result

### Specifying a fallback for viewport-based selection

When using viewport-bases selection of an image from a `srcset` by also specifying the [`sizes`](sizes) property, the `src` property serves as the fallback to be used on browsers that don't support viewport-based selection. Browsers that *do* support viewport-based selection will ignore `src` in this situation.

#### HTML

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-src">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.src' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/src</a>
