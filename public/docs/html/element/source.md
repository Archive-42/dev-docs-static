&lt;source&gt;: The Media or Image Source element
=================================================

The `<source>` specifies multiple media resources for the [`<picture>`](picture), the [`<audio>`](audio) element, or the [`<video>`](video) element. It is an empty element, meaning that it has no content and does not have a closing tag. It is commonly used to offer the same media content in multiple file formats in order to provide compatibility with a broad range of browsers given their differing support for [image file formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types) and [media file formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>It must have a start tag, but must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>A media element—<a href="audio"><code>&lt;audio&gt;</code></a> or <a href="video"><code>&lt;video&gt;</code></a>—and it must be placed before any <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a> or <a href="track"><code>&lt;track&gt;</code></a> element. A <a href="picture"><code>&lt;picture&gt;</code></a> element, and it must be placed before the <a href="img"><code>&lt;img&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement"><code>HTMLSourceElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`media`  
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries" class="internal">Media query</a> of the resource's intended media; this should be used only in a [`<picture>`](picture) element.

`sizes`  
Is a list of source sizes that describes the final rendered width of the image represented by the source. Each source size consists of a comma-separated list of media condition-length pairs. This information is used by the browser to determine, before laying the page out, which image defined in [`srcset`](#attr-srcset) to use. Please note that `sizes` will have its effect only if width dimension descriptors are provided with `srcset` instead of pixel ratio values (200w instead of 2x for example).

The `sizes` attribute has an effect only when the [`<source>`](source) element is the direct child of a [`<picture>`](picture) element.

`src`  
Required for [`<audio>`](audio) and [`<video>`](video), address of the media resource. The value of this attribute is ignored when the `<source>` element is placed inside a [`<picture>`](picture) element.

`srcset`  
A list of one or more strings separated by commas indicating a set of possible images represented by the source for the browser to use. Each string is composed of:

1.  One URL specifying an image.
2.  A width descriptor, which consists of a string containing a positive integer directly followed by `"w"`, such as `300w`. The default value, if missing, is the infinity.
3.  A pixel density descriptor, that is a positive floating number directly followed by `"x"`. The default value, if missing, is `1x`.

Each string in the list must have at least a width descriptor or a pixel density descriptor to be valid. Among the list, there must be only one string containing the same tuple of width descriptor and pixel density descriptor. The browser chooses the most adequate image to display at a given point of time.

The `srcset` attribute has an effect only when the [`<source>`](source) element is the direct child of a [`<picture>`](picture) element.

`type`  
The [MIME media type of the resource](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types), optionally with a [`codecs` parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter).

If the `type` attribute isn't specified, the media's type is retrieved from the server and checked to see if the user agent can handle it; if it can't be rendered, the next `<source>` is checked. If the `type` attribute is specified, it's compared against the types the user agent can present, and if it's not recognized, the server doesn't even get queried; instead, the next `<source>` element is checked at once.

When used in the context of a `<picture>` element, the browser will fall back to using the image specified by the `<picture>` element's [`<img>`](img) child if it is unable to find a suitable image to use after examining every provided `<source>`.

Usage notes
-----------

The `<source>` element is an **empty element (or void element)**, which means that it not only has no content but also has no closing tag. That is, you *never* use "`</source>`" in your HTML.

For information about image formats supported by web browsers and guidance on selecting appropriate formats to use, see our [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types) on the web. For details on the video and audio media types, you can use, see the [Guide to media types formats used on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats).

Examples
--------

### Video example

This example demonstrates how to offer a video in Ogg format for users whose browsers support Ogg format, and a QuickTime format video for users whose browsers support that. If the `audio` or `video` element is not supported by the browser, a notice is displayed instead. If the browser supports the element but does not support any of the specified formats, an `error` event is raised and the default media controls (if enabled) will indicate an error. Be sure to reference our [guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats) for details on what media file formats you can use and how well they're supported by browsers.

    <video controls>
      <source src="foo.webm" type="video/webm">
      <source src="foo.ogg" type="video/ogg">
      <source src="foo.mov" type="video/quicktime">
      I'm sorry; your browser doesn't support HTML5 video.
    </video>

For more examples, the learning area article [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content) is a great resource.

### Picture example

In this example, two `<source>` elements are included within the [`<picture>`](picture), providing versions of an image to use when the available space exceeds certain widths. If the available width is less than the smaller of these widths, the user agent will fall back to the image given by the [`<img>`](img) element.

    <picture>
       <source srcset="mdn-logo-wide.png" media="(min-width: 800px)">
       <source srcset="mdn-logo-medium.png" media="(min-width: 600px)">
       <img src="mdn-logo-narrow.png" alt="MDN Web Docs">
    </picture>

With the `<picture>` element, you must always include an `<img>` with a fallback image, with an `alt` attribute to ensure accessibility (unless the image is an irrelevant background decorative image).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-source-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;source&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`source`

Yes

12

3.5

Until Firefox 15, Firefox picked the first source element that has a type matching the MIME-type of a supported media format; see [bug 449363](https://bugzil.la/449363) for details.

9

Yes

Yes

Yes

Yes

4

Until Firefox 15, Firefox picked the first source element that has a type matching the MIME-type of a supported media format; see [bug 449363](https://bugzil.la/449363) for details.

Yes

Yes

Yes

`media`

Yes

12

15

9

Yes

Yes

Yes

Yes

15

?

Yes

Yes

`sizes`

38

34-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

≤18

38

?

25

21-25

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

9

7

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

≤37-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

34-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

25

21-25

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

9

8

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

3.0

2.0-3.0

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

`src`

Yes

12

3.5

9

Yes

Yes

Yes

Yes

4

?

Yes

Yes

`srcset`

38

34-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

≤18

38

?

25

21-25

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

9

7

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

≤37-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

34-38

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

38

25

21-25

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

9

8

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

3.0

2.0-3.0

Supports a subset of the syntax for resolution switching (using the `x` descriptor), but not the full syntax that can be used with `sizes` (using the `w` descriptor).

`type`

Yes

12

3.5

9

Yes

Yes

Yes

Yes

4

?

Yes

Yes

See also
--------

-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
-   [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
-   [`<picture>`](picture) element
-   [`<audio>`](audio) element
-   [`<video>`](video) element
-   [Web Performance](https://developer.mozilla.org/en-US/docs/Learn/Performance)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source</a>
