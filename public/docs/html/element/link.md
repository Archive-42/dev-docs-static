&lt;link&gt;: The External Resource Link element
================================================

The `<link>` specifies relationships between the current document and an external resource. This element is most commonly used to link to [stylesheets](https://developer.mozilla.org/en-US/docs/Glossary/CSS), but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.

To link an external stylesheet, you'd include a `<link>` element inside your [`<head>`](head) like this:

    <link href="main.css" rel="stylesheet">

This simple example provides the path to the stylesheet inside an `href` attribute, and a `rel` attribute with a value of `stylesheet`. The `rel` stands for "relationship", and is probably one of the key features of the `<link>` element — the value denotes how the item being linked to is related to the containing document. As you'll see from our [Link types](../link_types) reference, there are many different kinds of relationship.

There are a number of other common types you'll come across. For example, a link to the site's favicon:

    <link rel="icon" href="favicon.ico">

There are a number of other icon `rel` values, mainly used to indicate special icon types for use on various mobile platforms, e.g.:

    <link rel="apple-touch-icon-precomposed" sizes="114x114"
          href="apple-icon-114.png" type="image/png">

The `sizes` attribute indicates the icon size, while the `type` contains the MIME type of the resource being linked. These provide useful hints to allow the browser to choose the most appropriate icon available.

You can also provide a media type or query inside a `media` attribute; this resource will then only be loaded if the media condition is true. For example:

    <link href="print.css" rel="stylesheet" media="print">
    <link href="mobile.css" rel="stylesheet" media="screen and (max-width: 600px)">

Some interesting new performance and security features have been added to the `<link>` element too. Take this example:

    <link rel="preload" href="myFont.woff2" as="font"
          type="font/woff2" crossorigin="anonymous">

A `rel` value of `preload` indicates that the browser should preload this resource (see [Preloading content with rel="preload"](../preloading_content) for more details), with the `as` attribute indicating the specific class of content being fetched. The `crossorigin` attribute indicates whether the resource should be fetched with a [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request.

Other usage notes:

-   A `<link>` element can occur either in the [`<head>`](head) or [`<body>`](body) element, depending on whether it has a [link type](https://html.spec.whatwg.org/multipage/links.html#body-ok) that is **body-ok**. For example, the `stylesheet` link type is body-ok, and therefore `<link rel="stylesheet">` is permitted in the body. However, this isn't a good practice to follow; it makes more sense to separate your `<link>` elements from your body content, putting them in the `<head>`.
-   When using `<link>` to establish a favicon for a site, and your site uses a Content Security Policy (CSP) to enhance its security, the policy applies to the favicon. If you encounter problems with the favicon not loading, verify that the [`Content-Security-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) header's [`img-src` directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/img-src) is not preventing access to it.
-   The HTML and XHTML specifications define event handlers for the `<link>` element, but it is unclear how they would be used.
-   Under XHTML 1.0, empty elements such as `<link>` require a trailing slash: `<link />`.
-   WebTV supports the use of the value `next` for `rel` to preload the next page in a document series.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`as`  
This attribute is only used when `rel="preload"` or `rel="prefetch"` has been set on the `<link>` element. It specifies the type of content being loaded by the `<link>`, which is necessary for request matching, application of correct [content security policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP), and setting of correct [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) request header. Furthermore, `rel="preload"` uses this as a signal for request prioritization. The table below lists the valid values for this attribute and the elements or resources they apply to.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Value</th><th>Applies To</th></tr></thead><tbody><tr class="odd"><td>audio</td><td><code>&lt;audio&gt;</code> elements</td></tr><tr class="even"><td>document</td><td><code>&lt;iframe&gt;</code> and <code>&lt;frame&gt;</code> elements</td></tr><tr class="odd"><td>embed</td><td><code>&lt;embed&gt;</code> elements</td></tr><tr class="even"><td>fetch</td><td><p>fetch, XHR</p><div class="notecard note"><p>This value also requires <code>&lt;link&gt;</code> to contain the crossorigin attribute.</p></div></td></tr><tr class="odd"><td>font</td><td>CSS @font-face</td></tr><tr class="even"><td>image</td><td><code>&lt;img&gt;</code> and <code>&lt;picture&gt;</code> elements with srcset or imageset attributes, SVG <code>&lt;image&gt;</code> elements, CSS <code>*-image</code> rules</td></tr><tr class="odd"><td>object</td><td><code>&lt;object&gt;</code> elements</td></tr><tr class="even"><td>script</td><td><code>&lt;script&gt;</code> elements, Worker <code>importScripts</code></td></tr><tr class="odd"><td>style</td><td><code>&lt;link rel=stylesheet&gt;</code> elements, CSS <code>@import</code></td></tr><tr class="even"><td>track</td><td><code>&lt;track&gt;</code> elements</td></tr><tr class="odd"><td>video</td><td><code>&lt;video&gt;</code> elements</td></tr><tr class="even"><td>worker</td><td>Worker, SharedWorker</td></tr></tbody></table>

`crossorigin`  
This enumerated attribute indicates whether [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) must be used when fetching the resource. [CORS-enabled images](../cors_enabled_image) can be reused in the [`<canvas>`](canvas) element without being *tainted*. The allowed values are:

`anonymous`  
A cross-origin request (i.e. with an [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin) HTTP header) is performed, but no credential is sent (i.e. no cookie, X.509 certificate, or HTTP Basic authentication). If the server does not give credentials to the origin site (by not setting the [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Origin) HTTP header) the resource will be tainted and its usage restricted.

`use-credentials`  
A cross-origin request (i.e. with an `Origin` HTTP header) is performed along with a credential sent (i.e. a cookie, certificate, and/or HTTP Basic authentication is performed). If the server does not give credentials to the origin site (through [`Access-Control-Allow-Credentials`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Credentials) HTTP header), the resource will be *tainted* and its usage restricted.

If the attribute is not present, the resource is fetched without a [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request (i.e. without sending the `Origin` HTTP header), preventing its non-tainted usage. If invalid, it is handled as if the enumerated keyword **anonymous** was used. See [CORS settings attributes](../attributes/crossorigin) for additional information.

`disabled`  
For `rel="stylesheet"` only, the `disabled` Boolean attribute indicates whether or not the described stylesheet should be loaded and applied to the document. If `disabled` is specified in the HTML when it is loaded, the stylesheet will not be loaded during page load. Instead, the stylesheet will be loaded on-demand, if and when the `disabled` attribute is changed to `false` or removed.

Setting the `disabled` property in the DOM causes the stylesheet to be removed from the document's [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) list.

`href`  
This attribute specifies the [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL) of the linked resource. A URL can be absolute or relative.

`hreflang`  
This attribute indicates the language of the linked resource. It is purely advisory. Allowed values are determined by [BCP47](https://www.ietf.org/rfc/bcp/bcp47.txt). Use this attribute only if the [`href`](a#attr-href) attribute is present.

`imagesizes`  
For `rel="preload"` and `as="image"` only, the `imagesizes` attribute is [a sizes attribute](https://html.spec.whatwg.org/multipage/images.html#sizes-attribute) that indicates to preload the appropriate resource used by an `img` element with corresponding values for its `srcset` and `sizes` attributes.

`imagesrcset`  
For `rel="preload"` and `as="image"` only, the `imagesrcset` attribute is [a sourceset attribute](https://html.spec.whatwg.org/multipage/images.html#srcset-attribute) that indicates to preload the appropriate resource used by an `img` element with corresponding values for its `srcset` and `sizes` attributes.

 `integrity` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Contains inline metadata — a base64-encoded cryptographic hash of the resource (file) you’re telling the browser to fetch. The browser can use this to verify that the fetched resource has been delivered free of unexpected manipulation. See [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity).

`media`  
This attribute specifies the media that the linked resource applies to. Its value must be a media type / [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries). This attribute is mainly useful when linking to external stylesheets — it allows the user agent to pick the best adapted one for the device it runs on.

**Notes:**

-   In HTML 4, this can only be a simple white-space-separated list of media description literals, i.e., [media types and groups](https://developer.mozilla.org/en-US/docs/Web/CSS/@media), where defined and allowed as values for this attribute, such as `print`, `screen`, `aural`, `braille`. HTML5 extended this to any kind of [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries), which are a superset of the allowed values of HTML 4.
-   Browsers not supporting [CSS3 Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) won't necessarily recognize the adequate link; do not forget to set fallback links, the restricted set of media queries defined in HTML 4.

 `prefetch` <span class="notecard inline secure">Secure context</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Identifies a resource that might be required by the next navigation and that the user agent should retrieve it. This allows the user agent to respond faster when the resource is requested in the future.

 `referrerpolicy` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A string indicating which referrer to use when fetching the resource:

-   `no-referrer` means that the [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will not be sent.
-   `no-referrer-when-downgrade` means that no [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header will be sent when navigating to an origin without TLS (HTTPS). This is a user agent’s default behavior, if no policy is otherwise specified.
-   `origin` means that the referrer will be the origin of the page, which is roughly the scheme, the host, and the port.
-   `origin-when-cross-origin` means that navigating to other origins will be limited to the scheme, the host, and the port, while navigating on the same origin will include the referrer's path.
-   `unsafe-url` means that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe because it can leak origins and paths from TLS-protected resources to insecure origins.

`rel`  
This attribute names a relationship of the linked document to the current document. The attribute must be a space-separated list of [link type values](../link_types).

`sizes`  
This attribute defines the sizes of the icons for visual media contained in the resource. It must be present only if the [`rel`](#attr-rel) contains a value of `icon` or a non-standard type such as Apple's `apple-touch-icon`. It may have the following values:

-   `any`, meaning that the icon can be scaled to any size as it is in a vector format, like `image/svg+xml`.
-   a white-space separated list of sizes, each in the format `<width in pixels>x<height in pixels>` or `<width in pixels>X<height in pixels>`. Each of these sizes must be contained in the resource.

**Note:** Most icon formats are only able to store one single icon; therefore most of the time the [`sizes`](../global_attributes#attr-sizes) attribute contains only one entry. MS's ICO format does, as well as Apple's ICNS. ICO is more ubiquitous, so you should use this format if cross-browser support is a concern (especially for old IE versions).

`title`  
The `title` attribute has special semantics on the `<link>` element. When used on a `<link rel="stylesheet">` it defines a [preferred or an alternate stylesheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets). Incorrectly using it may [cause the stylesheet to be ignored](https://developer.mozilla.org/en-US/docs/Correctly_Using_Titles_With_External_Stylesheets).

`type`  
This attribute is used to define the type of the content linked to. The value of the attribute should be a MIME type such as **text/html**, **text/css**, and so on. The common use of this attribute is to define the type of stylesheet being referenced (such as **text/css**), but given that CSS is the only stylesheet language used on the web, not only is it possible to omit the `type` attribute, but is actually now recommended practice. It is also used on `rel="preload"` link types, to make sure the browser only downloads file types that it supports.

### Non-standard attributes

 `methods` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The value of this attribute provides information about the functions that might be performed on an object. The values generally are given by the HTTP protocol when it is used, but it might (for similar reasons as for the **title** attribute) be useful to include advisory information in advance in the link. For example, the browser might choose a different rendering of a link as a function of the methods specified; something that is searchable might get a different icon, or an outside link might render with an indication of leaving the current site. This attribute is not well understood nor supported, even by the defining browser, Internet Explorer 4.

 `target` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Defines the frame or window name that has the defined linking relationship or that will show the rendering of any linked resource.

### Obsolete attributes

 `charset` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines the character encoding of the linked resource. The value is a space- and/or comma-delimited list of character sets as defined in [RFC 2045](https://tools.ietf.org/html/rfc2045). The default value is `iso-8859-1`.

**Usage note:** To produce the same effect as this obsolete attribute, use the [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) HTTP header on the linked resource.

 `rev` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The value of this attribute shows the relationship of the current document to the linked document, as defined by the [`href`](#attr-href) attribute. The attribute thus defines the reverse relationship compared to the value of the `rel` attribute. [Link type values](../link_types) for the attribute are similar to the possible values for [`rel`](#attr-rel).

**Note:** This attribute is considered obsolete by the WHATWG HTML living standard (which is the specification MDN treats as canonical). However, it's worth noting that `rev` is *not* considered obsolete in the W3C specification. That said, given the uncertainty, relying on `rev` is unwise.

Instead, you should use the [`rel`](#attr-rel) attribute with the opposite [link type value](../link_types). For example, to establish the reverse link for `made`, specify `author`. Also this attribute doesn't stand for "revision" and must not be used with a version number, even though many sites misuse it in this way.

Examples
--------

### Including a stylesheet

To include a stylesheet in a page, use the following syntax:

    <link href="style.css" rel="stylesheet">

### Providing alternative stylesheets

You can also specify [alternative style sheets](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets).

The user can choose which style sheet to use by choosing it from the View &gt; Page Style menu. This provides a way for users to see multiple versions of a page.

    <link href="default.css" rel="stylesheet" title="Default Style">
    <link href="fancy.css" rel="alternate stylesheet" title="Fancy">
    <link href="basic.css" rel="alternate stylesheet" title="Basic">

### Providing icons for different usage contexts

You can include links to several different icons on the same page, and the browser will choose which one works best for its particular context using the `rel` and `sizes` values as hints.

    <!-- third-generation iPad with high-resolution Retina display: -->
    <link rel="apple-touch-icon-precomposed" sizes="144x144" href="favicon144.png">
    <!-- iPhone with high-resolution Retina display: -->
    <link rel="apple-touch-icon-precomposed" sizes="114x114" href="favicon114.png">
    <!-- first- and second-generation iPad: -->
    <link rel="apple-touch-icon-precomposed" sizes="72x72" href="favicon72.png">
    <!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
    <link rel="apple-touch-icon-precomposed" href="favicon57.png">
    <!-- basic favicon -->
    <link rel="icon" href="favicon32.png">

### Conditionally loading resources with media queries

You can provide a media type or query inside a `media` attribute; this resource will then only be loaded if the media condition is true. For example:

    <link href="print.css" rel="stylesheet" media="print">
    <link href="mobile.css" rel="stylesheet" media="all">
    <link href="desktop.css" rel="stylesheet" media="screen and (min-width: 600px)">
    <link href="highres.css" rel="stylesheet" media="screen and (min-resolution: 300dpi)">

### Stylesheet load events

You can determine when a style sheet has been loaded by watching for a `load` event to fire on it; similarly, you can detect if an error has occurred while processing a style sheet by watching for an `error` event:

    <script>
    var myStylesheet = document.querySelector('#my-stylesheet');

    myStylesheet.onload = function() {
      // Do something interesting; the sheet has been loaded
    }

    myStylesheet.onerror = function() {
      console.log("An error occurred loading the stylesheet!");
    }
    </script>

    <link rel="stylesheet" href="mystylesheet.css" id="my-stylesheet">

**Note:** The `load` event fires once the stylesheet and all of its imported content has been loaded and parsed, and immediately before the styles start being applied to the content.

### Preload examples

You can find a number of `<link rel="preload">` examples in [Preloading content with `rel="preload"`](../preloading_content).

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>Metadata content. If <code>itemprop</code> is present: <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a> and <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>As it is a void element, the start tag must be present and the end tag must not be present</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts metadata elements. If <a href="../global_attributes/itemprop">itemprop</a> is present: any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>link</code> with <code>href</code> attribute</td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement"><code>HTMLLinkElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-link-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;link&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>imagesizes</code> and <code>imagesrcset</code> attributes.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-link-element">HTML5<br />
<span class="small">The definition of '&lt;link&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>crossorigin</code> and <code>sizes</code> attributes; extended values of <code>media</code> to any media queries; added numerous new values for <code>rel</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/links.html#h-12.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;link&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`link`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`charset`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`crossorigin`

25

79

18

Before Firefox 83, `crossorigin` is not supported for `rel="icon"`.

No

15

?

37

Yes

18

?

?

Yes

`disabled`

1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

12

Since Edge 79, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

1

≤6

≤12.1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

≤4

1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

18

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

4

≤12.1

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

≤3

1.0

In Chrome and other Blink-based browsers, adding the `disabled` attribute using JavaScript does not remove the stylesheet from `document.styleSheets`.

`href`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`hreflang`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`imagesizes`

73

79

78

No

60

No

73

73

79

52

No

11.0

`imagesrcset`

73

79

78

No

60

No

73

73

79

52

No

11.0

`integrity`

45

17

43

No

32

11.1

45

45

43

32

11.3

5.0

`media`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`methods`

No

12-79

No

4

No

No

No

No

No

No

No

No

`prefetch`

56

≤79

?

No

43

?

56

56

?

43

?

6.0

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

`rel`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`rev`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`sizes`

No

No

No

See [bug 441770](https://bugzil.la/441770).

No

No

No

No

No

No

See [bug 441770](https://bugzil.la/441770).

No

No

No

`target`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`title`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`type`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

See also
--------

-   [`Link`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link) HTTP header

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link</a>
