&lt;img&gt;: The Image Embed element
====================================

The `<img>` embeds an image into the document.

The above example shows usage of the `<img>` element:

-   The `src` attribute is **required**, and contains the path to the image you want to embed.
-   The `alt` attribute holds a text description of the image, which isn't mandatory but is **incredibly useful** for accessibility — screen readers read this description out to their users so they know what the image means. Alt text is also displayed on the page if the image can't be loaded for some reason: for example, network errors, content blocking, or linkrot.

There are many other attributes to achieve various purposes:

-   [Referrer](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)/[CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) control for security and privacy: see [`crossorigin`](#attr-crossorigin) and [`referrerpolicy`](#attr-referrerpolicy).
-   Use both [`width`](#attr-width) and [`height`](#attr-height) to set the intrinsic size of the image, allowing it to take up space before it loads, to mitigate content layout shifts.
-   Responsive image hints with [`sizes`](#attr-sizes) and [`srcset`](#attr-srcset) (see also the [`<picture>`](picture) element and our [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) tutorial).

Supported image formats
-----------------------

The HTML standard doesn't list what image formats to support, so each [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) supports different formats.

The image file formats that are most commonly used on the web are listed below.

<table><colgroup><col style="width: 20%" /><col style="width: 20%" /><col style="width: 20%" /><col style="width: 20%" /><col style="width: 20%" /></colgroup><thead><tr class="header"><th>Abbreviation</th><th>File format</th><th>MIME type</th><th>File extension(s)</th><th>Summary</th></tr></thead><tbody><tr class="odd"><td><a href="#apng">APNG</a></td><td>Animated Portable Network Graphics</td><td><code>image/apng</code></td><td><code>.apng</code></td><td>Good choice for lossless animation sequences (GIF is less performant). <a href="#avif">AVIF</a> and <a href="#webp">WebP</a> have better performance but less broad browser support.<br />
<strong>Supported</strong>: Chrome, Edge, Firefox, Opera, Safari.</td></tr><tr class="even"><td><a href="#avif">AVIF</a></td><td>AV1 Image File Format</td><td><code>image/avif</code></td><td><code>.avif</code></td><td><p>Good choice for both images and animated images due to high performance and royalty free image format. It offers much better compression than <a href="#png">PNG</a> or <a href="#jpeg">JPEG</a> with support for higher color depths, animated frames, transparency etc. Note that when using AVIF, you should include fallbacks to formats with better browser support (i.e. using the <code>&lt;picture&gt;</code> element).<br />
<strong>Supported:</strong> Chrome, Opera, Firefox (behind a <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Experimental_features#avif_av1_image_file_format_support">preference</a>. Basic support only; advanced features like animated images and colorspace support yet to the implemented).</p></td></tr><tr class="odd"><td><a href="#gif">GIF</a></td><td>Graphics Interchange Format</td><td><code>image/gif</code></td><td><code>.gif</code></td><td>Good choice for simple images and animations. Prefer <a href="#png">PNG</a> for lossless <em>and</em> indexed still images, and consider <a href="#webp">WebP</a>, <a href="#avif">AVIF</a> or <a href="#apng">APNG</a> for animation sequences.<br />
<strong>Supported:</strong> Chrome, Edge, Firefox, IE, Opera, Safari.</td></tr><tr class="even"><td><a href="#jpeg">JPEG</a></td><td>Joint Photographic Expert Group image</td><td><code>image/jpeg</code></td><td><code>.jpg</code>, <code>.jpeg</code>, <code>.jfif</code>, <code>.pjpeg</code>, <code>.pjp</code></td><td><p>Good choice for lossy compression of still images (currently the most popular). Prefer <a href="#png">PNG</a> when more precise reproduction of the image is required, or <a href="#webp">WebP</a>/<a href="#avif">AVIF</a> if both better reproduction and higher compression are required.<br />
<strong>Support:</strong> Chrome, Edge, Firefox, IE, Opera, Safari.</p></td></tr><tr class="odd"><td><a href="#png">PNG</a></td><td>Portable Network Graphics</td><td><code>image/png</code></td><td><code>.png</code></td><td><p>PNG is preferred over JPEG for more precise reproduction of source images, or when transparency is needed. <a href="#webp">WebP</a>/<a href="#avif">AVIF</a> provide even better compression and reproduction, but browser support is more limited.<br />
<strong>Support:</strong> Chrome, Edge, Firefox, IE, Opera, Safari.</p></td></tr><tr class="even"><td><a href="#svg">SVG</a></td><td>Scalable Vector Graphics</td><td><code>image/svg+xml</code></td><td><code>.svg</code></td><td>Vector image format; ideal for user interface elements, icons, diagrams, etc., that must be drawn accurately at different sizes.<br />
<strong>Support:</strong> Chrome, Edge, Firefox, IE, Opera, Safari.</td></tr><tr class="odd"><td><a href="#webp">WebP</a></td><td>Web Picture format</td><td><code>image/webp</code></td><td><code>.webp</code></td><td>Excellent choice for both images and animated images. WebP offers much better compression than <a href="#png">PNG</a> or <a href="#jpeg">JPEG</a> with support for higher color depths, animated frames, transparency etc. <a href="#avif">AVIF</a> offers slightly better compression, but is not quite as well-supported in browsers and does not support progressive rendering.<br />
<strong>Support:</strong> Chrome, Edge, Firefox, Opera, Safari</td></tr></tbody></table>

**Note**

The older formats like PNG, JPEG, GIF have poor performance compared to newer formats like WebP and AVIF, but enjoy broader "historical" browser support. The newer image formats are seeing increasing popularity as browsers without support become increasingly irrelevant (i.e. have virtually zero market share).

The following list includes image formats that appear on the web, but which should be avoided for web content (generally this is because either they do not have wide browser support, or because there are better alternatives).

<table><thead><tr class="header"><th>Abbreviation</th><th>File format</th><th>MIME type</th><th>File extension(s)</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="#bmp">BMP</a></td><td>Bitmap file</td><td><code>image/bmp</code></td><td><code>.bmp</code></td><td>Chrome, Edge, Firefox, IE, Opera, Safari</td></tr><tr class="even"><td><a href="#ico">ICO</a></td><td>Microsoft Icon</td><td><code>image/x-icon</code></td><td><code>.ico</code>, <code>.cur</code></td><td>Chrome, Edge, Firefox, IE, Opera, Safari</td></tr><tr class="odd"><td><a href="#tiff">TIFF</a></td><td>Tagged Image File Format</td><td><code>image/tiff</code></td><td><code>.tif</code>, <code>.tiff</code></td><td>Safari</td></tr></tbody></table>

**Note**

The abbreviation for each image format links to a longer description of the format, its capabilities, and detailed browser compatibility information (including which versions introduced support and specific special features that may have been introduced later).

**Tip**

See [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types) for more comprehensive information about image formats supported by web browsers. This includes image formats that are supported but not recommended for web content (e.g. ICO, BMP, etc.)

Image loading errors
--------------------

If an error occurs while loading or rendering an image, and an [`onerror`](../global_attributes#attr-onerror) event handler has been set on the `error` event, that event handler will get called. This can happen in a number of situations, including:

-   The `src` attribute is empty (`""`) or `null`.
-   The `src` [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) is the same as the URL of the page the user is currently on.
-   The image is corrupted in some way that prevents it from being loaded.
-   The image's metadata is corrupted in such a way that it's impossible to retrieve its dimensions, and no dimensions were specified in the `<img>` element's attributes.
-   The image is in a format not supported by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

Attributes
----------

This element includes the [global attributes](../global_attributes).

`alt`  
Defines an alternative text description of the image.

**Note**
Browsers do not always display images. There are a number of situations in which a browser might not display images, such as:

-   Non-visual browsers (such as those used by people with visual impairments)
-   The user chooses not to display images (saving bandwidth, privacy reasons)
-   The image is invalid or an [unsupported type](#supported_image_formats)

In these cases, the browser may replace the image with the text in the element's `alt` attribute. For these reasons and others, provide a useful value for `alt` whenever possible.

Omitting `alt` altogether indicates that the image is a key part of the content and no textual equivalent is available. Setting this attribute to an empty string (`alt=""`) indicates that this image is *not* a key part of the content (it’s decoration or a tracking pixel), and that non-visual browsers may omit it from [rendering](https://developer.mozilla.org/en-US/docs/Glossary/Rendering_engine). Visual browsers will also hide the broken image icon if the `alt` is empty and the image failed to display.

This attribute is also used when copying and pasting the image to text, or saving a linked image to a bookmark.

`crossorigin`  
Indicates if the fetching of the image must be done using a [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request. Image data from a [CORS-enabled image](../cors_enabled_image) returned from a CORS request can be reused in the [`<canvas>`](canvas) element without being marked "[tainted](../cors_enabled_image#what_is_a_tainted_canvas)".

If the `crossorigin` attribute is *not* specified, then a non-CORS request is sent (without the [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin) request header), and the browser marks the image as tainted and restricts access to its image data, preventing its usage in [`<canvas>`](canvas) elements.

If the `crossorigin` attribute *is* specified, then a CORS request is sent (with the [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin) request header); but if the server does not opt into allowing cross-origin access to the image data by the origin site (by not sending any [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin) response header, or by not including the site's origin in any [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin) response header it does send), then the browser marks the image as tainted and restricts access to its image data, preventing its usage in [`<canvas>`](canvas) elements.

Allowed values:

`anonymous`  
A CORS request is sent with credentials omitted (that is, no [cookies](https://developer.mozilla.org/en-US/docs/Glossary/Cookie), [X.509 certificates](https://datatracker.ietf.org/doc/html/rfc5280), or [`Authorization`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) request header).

`use-credentials`  
The CORS request is sent with any credentials included (that is, cookies, X.509 certificates, and the `Authorization` request header). If the server does not opt into sharing credentials with the origin site (by sending back the `Access-Control-Allow-Credentials: true` response header), then the browser marks the image as tainted and restricts access to its image data.

If the attribute has an invalid value, browsers handle it as if the `anonymous` value was used. See [CORS settings attributes](../attributes/crossorigin) for additional information.

`decoding`  
Provides an image decoding hint to the browser. Allowed values:

`sync`  
Decode the image synchronously, for atomic presentation with other content.

`async`  
Decode the image asynchronously, to reduce delay in presenting other content.

`auto`  
Default: no preference for the decoding mode. The browser decides what is best for the user.

`height`  
The intrinsic height of the image, in pixels. Must be an integer without a unit.

 `intrinsicsize` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute tells the browser to ignore the actual [intrinsic size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size) of the image and pretend it’s the size specified in the attribute. Specifically, the image would raster at these dimensions and `naturalWidth`/`naturalHeight` on images would return the values specified in this attribute. [Explainer](https://github.com/ojanvafai/intrinsicsize-attribute), [examples](https://googlechrome.github.io/samples/intrinsic-size/index.html)

`ismap`  
This Boolean attribute indicates that the image is part of a [server-side map](https://en.wikipedia.org/wiki/Image_map#Server-side). If so, the coordinates where the user clicked on the image are sent to the server.

**Note**
**Note:** This attribute is allowed only if the `<img>` element is a descendant of an [`<a>`](a) element with a valid [`href`](a#attr-href) attribute. This gives users without pointing devices a fallback destination.

 `loading` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Indicates how the browser should load the image:

-   `eager`: Loads the image immediately, regardless of whether or not the image is currently within the visible viewport (this is the default value).
-   `lazy`: Defers loading the image until it reaches a calculated distance from the viewport, as defined by the browser. The intent is to avoid the network and storage bandwidth needed to handle the image until it's reasonably certain that it will be needed. This generally improves the performance of the content in most typical use cases.
    **Note**
    Loading is only deferred when JavaScript is enabled. This is an anti-tracking measure, because if a user agent supported lazy loading when scripting is disabled, it would still be possible for a site to track a user's approximate scroll position throughout a session, by strategically placing images in a page's markup such that a server can track how many images are requested and when.

 `referrerpolicy` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A string indicating which referrer to use when fetching the resource:

-   `no-referrer`: The [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent.
-   `no-referrer-when-downgrade`: No `Referer` header is sent when navigating to an origin without [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https). This is the default if no policy is otherwise specified.
-   `origin`: The `Referer` header will include the page's origin (<span class="page-not-created">scheme</span>, [host](https://developer.mozilla.org/en-US/docs/Glossary/Host), and [port](https://developer.mozilla.org/en-US/docs/Glossary/Port)).
-   `origin-when-cross-origin`: Navigating to other origins will limit the included referral data to the scheme, host, and port, while navigating from the same origin will include the full path and query string.
-   `unsafe-url`: The `Referer` header will always include the origin, path and query string, but not the fragment, password, or username. **This is unsafe** because it can leak information from TLS-protected resources to insecure origins.

`sizes`  
One or more strings separated by commas, indicating a set of source sizes. Each source size consists of:

1.  A [media condition](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#syntax). This must be omitted for the last item in the list.
2.  A source size value.

Media Conditions describe properties of the *viewport*, not of the *image*. For example, `(max-height: 500px) 1000px` proposes to use a source of 1000px width, if the *viewport* is not higher than 500px.

Source size values specify the intended display size of the image. [User agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) use the current source size to select one of the sources supplied by the `srcset` attribute, when those sources are described using width (`w`) descriptors. The selected source size affects the [intrinsic size](https://developer.mozilla.org/en-US/docs/Glossary/Intrinsic_Size) of the image (the image’s display size if no [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) styling is applied). If the `srcset` attribute is absent, or contains no values with a width descriptor, then the `sizes` attribute has no effect.

`src`  
The image [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL). Mandatory for the `<img>` element. On [browsers](https://developer.mozilla.org/en-US/docs/Glossary/Browser) supporting `srcset`, `src` is treated like a candidate image with a pixel density descriptor `1x`, unless an image with this pixel density descriptor is already defined in `srcset`, or unless `srcset` contains `w` descriptors.

`srcset`  
One or more strings separated by commas, indicating possible image sources for the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to use. Each string is composed of:

1.  A [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) to an image
2.  Optionally, whitespace followed by one of:
    -   A width descriptor (a positive integer directly followed by `w`). The width descriptor is divided by the source size given in the `sizes` attribute to calculate the effective pixel density.
    -   A pixel density descriptor (a positive floating point number directly followed by `x`).

If no descriptor is specified, the source is assigned the default descriptor of `1x`.

It is incorrect to mix width descriptors and pixel density descriptors in the same `srcset` attribute. Duplicate descriptors (for instance, two sources in the same `srcset` which are both described with `2x`) are also invalid.

The user agent selects any of the available sources at its discretion. This provides them with significant leeway to tailor their selection based on things like user preferences or [bandwidth](https://developer.mozilla.org/en-US/docs/Glossary/Bandwidth) conditions. See our [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) tutorial for an example.

`width`  
The intrinsic width of the image in pixels. Must be an integer without a unit.

`usemap`  
The partial [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) (starting with `#`) of an [image map](map) associated with the element.

**Note**
You cannot use this attribute if the `<img>` element is inside an [`<a>`](a) or [`<button>`](button) element.

### Deprecated attributes

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Aligns the image with its surrounding context. Use the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) and/or [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) properties instead of this attribute. Allowed values:

`top`  
Equivalent to `vertical-align: top` or `vertical-align: text-top`

`middle`  
Equivalent to `vertical-align: -moz-middle-with-baseline`

`bottom`  
The default, equivalent to `vertical-align: unset` or `vertical-align: initial`

`left`  
Equivalent to `float: left`

`right`  
Equivalent to `float: right`

 `border` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The width of a border around the image. Use the [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) property instead.

 `hspace` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The number of pixels of white space on the left and right of the image. Use the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) CSS property instead.

 `longdesc` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A link to a more detailed description of the image. Possible values are a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) or an element [`id`](../global_attributes#attr-id).

**Note**
This attribute is mentioned in the latest [W3C](https://developer.mozilla.org/en-US/docs/Glossary/W3C) version, [HTML 5.2](https://www.w3.org/TR/html52/obsolete.html#element-attrdef-img-longdesc), but has been removed from the [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG)’s [HTML Living Standard](https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element). It has an uncertain future; authors should use a [WAI](https://developer.mozilla.org/en-US/docs/Glossary/WAI)-[ARIA](https://developer.mozilla.org/en-US/docs/Glossary/ARIA) alternative such as [`aria-describedby`](https://www.w3.org/TR/wai-aria-1.1/#aria-describedby) or [`aria-details`](https://www.w3.org/TR/wai-aria-1.1/#aria-details).

 `name` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A name for the element. Use the [`id`](../global_attributes#attr-id) attribute instead.

 `vspace` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The number of pixels of white space above and below the image. Use the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) CSS property instead.

Styling with CSS
----------------

`<img>` is a [replaced element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element); it has a [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) value of `inline` by default, but its default dimensions are defined by the embedded image's intrinsic values, like it were `inline-block`. You can set properties like [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)/[`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius), [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)/[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin), [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), etc. on an image.

`<img>` has no baseline, so when images are used in an inline formatting context with [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)`: baseline`, the bottom of the image will be placed on the text baseline.

You can use the [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) property to position the image within the element's box, and the [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) property to adjust the sizing of the image within the box (for example, whether the image should fit the box or fill it even if clipping is required).

Depending on its type, an image may have an intrinsic width and height. For some image types, however, intrinsic dimensions are unnecessary. [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG) images, for instance, have no intrinsic dimensions if their root [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) element doesn't have a `width` or `height` set on it.

Examples
--------

### Alternative text

The following example embeds an image into the page and includes alternative text for accessibility.

    <img src="https://developer.mozilla.org/static/img/favicon144.png"
         alt="MDN logo">

### Image link

This example builds upon the previous one, showing how to turn the image into a link. To do so, nest the `<img>` tag inside the [`<a>`](a). You should made the alternative text describe the resource the link is pointing to, as if you were using a text link instead.

    <a href="https://developer.mozilla.org">
      <img src="https://developer.mozilla.org/static/img/favicon144.png"
           alt="Visit the MDN site">
    </a>

### Using the srcset attribute

In this example we include a `srcset` attribute with a reference to a high-resolution version of the logo; this will be loaded instead of the `src` image on high-resolution devices. The image referenced in the `src` attribute is counted as a `1x` candidate in [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that support `srcset`.

     <img src="https://developer.mozilla.org/static/img/favicon72.png"
          alt="MDN logo"
          srcset="https://developer.mozilla.org/static/img/favicon144.png 2x">

### Using the srcset and sizes attributes

The `src` attribute is ignored in [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that support `srcset` when `w` descriptors are included. When the `(max-width: 600px)` media condition matches, the 200 pixel-wide image will load (it is the one that matches `200px` most closely), otherwise the other image will load.

     <img src="/files/16864/clock-demo-200px.png"
          alt="Clock"
          srcset="/files/16864/clock-demo-200px.png 200w,
              /files/16797/clock-demo-400px.png 400w"
          sizes="(max-width: 600px) 200px, 50vw">

**Note**

To see the resizing in action, [view the example on a separate page](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/HTML/Element/img/_samples_/Using_the_srcset_and_sizes_attributes), so you can actually resize the content area.

Security and privacy concerns
-----------------------------

Although `<img>` elements have innocent uses, they can have undesirable consequences for user security and privacy. See [Referer header: privacy and security concerns](https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns) for more information and mitigations.

Accessibility concerns
----------------------

### Authoring meaningful alternate descriptions

An `alt` attribute's value should clearly and concisely describe the image's content. It should not describe the presence of the image itself or the file name of the image. If the `alt` attribute is purposefully left off because the image has no textual equivalent, consider alternate methods to present what the image is trying to communicate.

#### Don't

    <img alt="image" src="penguin.jpg">

#### Do

    <img alt="A Rockhopper Penguin standing on a beach." src="penguin.jpg">

When an `alt` attribute is not present on an image, some screen readers may announce the image's file name instead. This can be a confusing experience if the file name isn't representative of the image's contents.

-   [An alt Decision Tree • Images • WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/images/decision-tree/)
-   [Alt-texts: The Ultimate Guide — Axess Lab](https://axesslab.com/alt-texts/)
-   [How to Design Great Alt Text: An Introduction | Deque](https://www.deque.com/blog/great-alt-text-introduction/)
-   [MDN Understanding WCAG, Guideline 1.1 explanations](#)
-   [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/text-equiv-all.html)

### The title attribute

The [`title`](../global_attributes#attr-title) attribute is not an acceptable substitute for the `alt` attribute. Additionally, avoid duplicating the `alt` attribute's value in a `title` attribute declared on the same image. Doing so may cause some screen readers to announce the description twice, creating a confusing experience.

The `title` attribute should also not be used as supplemental captioning information to accompany an image's `alt` description. If an image needs a caption, use the `figure` and `figcaption` elements.

The value of the `title` attribute is usually presented to the user as a tooltip, which appears shortly after the cursor stops moving over the image. While this *can* provide additional information to the user, you should not assume that the user will ever see it: the user may only have keyboard or touchscreen. If you have information that's particularly important or valuable for the user, present it inline using one of the methods mentioned above instead of using `title`.

-   [Using the HTML title attribute – updated | The Paciello Group](https://developer.paciellogroup.com/blog/2013/01/using-the-html-title-attribute-updated/)

Technical summary
-----------------

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>. If the element has a <code>usemap</code> attribute, it also is a part of the interactive content category.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts embedded content.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><ul><li>with non-empty <code>alt</code> attribute or no <code>alt</code> attribute: <code>img</code></li><li>with empty <code>alt</code> attribute: <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></li></ul></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><ul><li>with non-empty <code>alt</code> attribute:<ul><li><code>button</code></li><li><code>checkbox</code></li><li><code>link</code></li><li><code>menuitem</code></li><li><code>menuitemcheckbox</code></li><li><code>menuitemradio</code></li><li><code>option</code></li><li><code>progressbar</code></li><li><code>scrollbar</code></li><li><code>separator</code></li><li><code>slider</code></li><li><code>switch</code></li><li><code>tab</code></li><li><code>treeitem</code></li></ul></li><li>with empty <code>alt</code> attribute, <code>none</code> or <code>presentation</code></li><li>with no <code>alt</code> attribute, no <code>role</code> permitted</li></ul></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement"><code>HTMLImageElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrer attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerpolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;img&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-img-element">HTML5<br />
<span class="small">The definition of '&lt;img&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;img&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`img`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`align`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`alt`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`aspect_ratio_computed_from_attributes`

79

79

71

69-71

No

66

14

79

79

79

57

14

12.0

`border`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`crossorigin`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`decoding`

Yes

≤79

63

No

Yes

11.1

Yes

Yes

63

Yes

11.3

Yes

`height`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`hspace`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`intrinsicsize`

71-78

No

No

No

58-65

No

No

71-78

No

50-56

No

No

`ismap`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

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

No

See [bug 1542784](https://bugzil.la/1542784)

55

No

See [bug 196698](https://webkit.org/b/196698)

12.0

`longdesc`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`name`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`onerror`

Yes

≤79

51

?

Yes

Yes

Yes

Yes

51

Yes

Yes

Yes

`referrerpolicy`

51

79

50

No

38

11.1

51

51

50

41

No

7.2

`sizes`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`src`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`srcset`

34

≤18

38

No

21

8

37

34

38

21

8

2.0

`usemap`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`vspace`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`width`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
-   [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
-   [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
-   [`<picture>`](picture), [`<object>`](object) and [`<embed>`](embed) elements
-   Other image-related CSS properties: [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit), [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position), [`image-orientation`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation), [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering), and [`image-resolution`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-resolution).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img</a>
