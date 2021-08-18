&lt;picture&gt;: The Picture element
====================================

The `<picture>` contains zero or more [`<source>`](source) elements and one [`<img>`](img) element to offer alternative versions of an image for different display/device scenarios.

The browser will consider each child `<source>` element and choose the best match among them. If no matches are found—or the browser doesn't support the `<picture>` element—the URL of the `<img>` element's [`src`](img#attr-src) attribute is selected. The selected image is then presented in the space occupied by the `<img>` element.

To decide which URL to load, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) examines each `<source>`'s [`srcset`](source#attr-srcset), [`media`](source#attr-media), and [`type`](source#attr-type) attributes to select a compatible image that best matches the current layout and capabilities of the display device.

The `<img>` element serves two purposes:

1.  It describes the size and other attributes of the image and its presentation.
2.  It provides a fallback in case none of the offered `<source>` elements are able to provide a usable image.

Common use cases for `<picture>`:

-   **Art direction.** Cropping or modifying images for different `media` conditions (for example, loading a simpler version of an image which has too many details, on smaller displays).
-   **Offering alternative image formats**, for cases where certain formats are not supported.
    **Note:** For example, newer formats like [AVIF](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#avif) or [WEBP](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#webp) have many advantages, but might not be supported by the browser. A list of supported image formats can be found in: [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types).

-   **Saving bandwidth and speeding page load times** by loading the most appropriate image for the viewer's display.

If providing higher-density versions of an image for high-DPI (Retina) display, use [`srcset`](img#attr-srcset) on the `<img>` element instead. This lets browsers opt for lower-density versions in data-saving modes, and you don't have to write explicit `media` conditions.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, phrasing content, embedded content</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="source"><code>&lt;source&gt;</code></a> elements, followed by one <a href="img"><code>&lt;img&gt;</code></a> element, optionally intermixed with script-supporting elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that allows embedded content.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLPictureElement"><code>HTMLPictureElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes only [global attributes](../global_attributes).

Usage notes
-----------

You can use the [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) property to adjust the positioning of the image within the element's frame, and the [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) property to control how the image is resized to fit within the frame.

**Note:** Use these properties on the child `<img>` element, **not** the `<picture>` element.

Examples
--------

These examples demonstrate how different attributes of the [`<source>`](source) element change the selection of the image inside `<picture>`.

### The media attribute

The `media` attribute specifies a media condition (similar to a media query) that the user agent will evaluate for each [`<source>`](source) element.

If the [`<source>`](source)'s media condition evaluates to `false`, the browser skips it and evaluates the next element inside `<picture>`.

    <picture>
      <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
      <img src="mdn-logo-narrow.png" alt="MDN">
    </picture>

### The srcset attribute

The [`srcset`](source#attr-srcset) attribute is used to offer list of possible images *based on size*.

It is composed of a comma-separated list of image descriptors. Each image descriptor is composed of a URL of the image, and *either...*

-   a *width descriptor*, followed by a `w` (such as `300w`);  
    *OR*
-   a *pixel density descriptor*, followed by an `x` (such as `2x`) to serve a high-res image for high-DPI screens.

<!-- -->

    <picture>
      <source srcset="logo-768.png 768w, logo-768-1.5x.png 1.5x">
      <source srcset="logo-480.png, logo-480-2x.png 2x">
      <img src="logo-320.png" alt="logo">
    </picture>

### The type attribute

The `type` attribute specifies a [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) for the resource URL(s) in the [`<source>`](source) element's `srcset` attribute. If the user agent does not support the given type, the [`<source>`](source) element is skipped.

    <picture>
      <source srcset="logo.webp" type="image/webp">
      <img src="logo.png" alt="logo">
    </picture>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-picture-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;picture&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`picture`

38

13

38

No

25

9.1

38

38

38

25

9.3

3.0

See also
--------

-   [`<img>`](img) element
-   [`<source>`](source) element
-   Positioning and sizing the picture within its frame: [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) and [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
-   [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture</a>
