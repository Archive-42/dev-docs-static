HTML attribute: rel
===================

**Draft**

This page is not complete.

The `rel` attribute defines the relationship between a linked resource and the current document. Valid on [`<link>`](../element/link), [`<a>`](../element/a), [`<area>`](../element/area), and [`<form>`](../element/form), the supported values depend on the element on which the attribute is found.

The type of relationships is given by the value of the `rel` attribute, which, if present, must have a value that is an unordered set of unique space-separated keywords. Differently from a `class` name, which does not express semantics, the `rel` attribute must express tokens that are semantically valid for both machines and humans. The current registries for the possible values of the `rel` attribute are the [IANA link relation registry](https://www.iana.org/assignments/link-relations/link-relations.xhtml), the [HTML Living Standard](https://html.spec.whatwg.org/multipage/links.html#linkTypes), and the freely-editable [existing-rel-values page](https://microformats.org/wiki/existing-rel-values) in the microformats wiki, [as suggested](https://html.spec.whatwg.org/multipage/links.html#other-link-types) by the Living Standard. If a `rel` attribute not present in one of the three sources above is used some HTML validators (such as the [W3C Markup Validation Service](https://validator.w3.org/)) will generate a warning.

The following table lists some of the most important existing keywords. Every keyword within a space-separated value should be unique within that value.

<table><caption>Values for the <code>rel</code> attribute, and the elements for which each is relevant</caption><thead><tr class="header"><th><code>rel</code> value</th><th>Description</th><th><code>&lt;link&gt;</code></th><th><code>&lt;a&gt;</code> and <code>&lt;area&gt;</code></th><th><code>&lt;form&gt;</code></th></tr></thead><tbody><tr class="odd"><td><code>alternate</code></td><td>Alternate representations of the current document.</td><td>Link</td><td>Link</td><td>Not allowed</td></tr><tr class="even"><td><code>author</code></td><td>Author of the current document or article.</td><td>Link</td><td>Link</td><td>Not allowed</td></tr><tr class="odd"><td><code>bookmark</code></td><td>Permalink for the nearest ancestor section.</td><td>Not allowed</td><td>Link</td><td>Not allowed</td></tr><tr class="even"><td><code>canonical</code></td><td>Preferred URL for the current document.</td><td>Link</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>dns-prefetch</code></td><td>Tells the browser to preemptively perform DNS resolution for the target resource's origin</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="even"><td><code>external</code></td><td>The referenced document is not part of the same site as the current document.</td><td>Not allowed</td><td>Annotation</td><td>Annotation</td></tr><tr class="odd"><td><code>help</code></td><td>Link to context-sensitive help.</td><td>Link</td><td>Link</td><td>Link</td></tr><tr class="even"><td><code>icon</code></td><td>An icon representing the current document.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>license</code></td><td>Indicates that the main content of the current document is covered by the copyright license described by the referenced document.</td><td>Link</td><td>Link</td><td>Link</td></tr><tr class="even"><td><code>manifest</code></td><td>Web app manifest</td><td>Link</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>modulepreload</code></td><td>Tells to browser to preemptively fetch the script and store it in the document's module map for later evaluation. Optionally, the module's dependencies can be fetched as well.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="even"><td><code>next</code></td><td>Indicates that the current document is a part of a series and that the next document in the series is the referenced document.</td><td>Link</td><td>Link</td><td>Link</td></tr><tr class="odd"><td><code>nofollow</code></td><td>Indicates that the current document's original author or publisher does not endorse the referenced document.</td><td>Not allowed</td><td>Annotation</td><td>Annotation</td></tr><tr class="even"><td><code>noopener</code></td><td>Creates a top-level browsing context that is not an auxiliary browsing context if the hyperlink would create either of those, to begin with (i.e., has an appropriate<code> target </code>attribute value).</td><td>Not allowed</td><td>Annotation</td><td>Annotation</td></tr><tr class="odd"><td><code>noreferrer</code></td><td>No <code>Referer</code> header will be included. Additionally, has the same effect as <code>noopener</code>.</td><td>Not allowed</td><td>Annotation</td><td>Annotation</td></tr><tr class="even"><td><code>opener</code></td><td>Creates an auxiliary browsing context if the hyperlink would otherwise create a top-level browsing context that is not an auxiliary browsing context (i.e., has "<code>_blank</code>" as <code>target</code> attribute value).</td><td>Not allowed</td><td>Annotation</td><td>Annotation</td></tr><tr class="odd"><td><code>pingback</code></td><td>Gives the address of the pingback server that handles pingbacks to the current document.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="even"><td><code>preconnect</code></td><td>Specifies that the user agent should preemptively connect to the target resource's origin.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>prefetch</code></td><td>Specifies that the user agent should preemptively fetch and cache the target resource as it is likely to be required for a followup navigation.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="even"><td><code>preload</code></td><td>Specifies that the user agent must preemptively fetch and cache the target resource for current navigation according to the potential destination given by the <code>as</code> attribute (and the priority associated with the corresponding destination).</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>prerender</code></td><td>Specifies that the user agent should preemptively fetch the target resource and process it in a way that helps deliver a faster response in the future.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="even"><td><code>prev</code></td><td>Indicates that the current document is a part of a series and that the previous document in the series is the referenced document.</td><td>Link</td><td>Link</td><td>Link</td></tr><tr class="odd"><td><code>search</code></td><td>Gives a link to a resource that can be used to search through the current document and its related pages.</td><td>Link</td><td>Link</td><td>Link</td></tr><tr class="even"><td><code>stylesheet</code></td><td>Imports a style sheet.</td><td>External Resource</td><td>Not allowed</td><td>Not allowed</td></tr><tr class="odd"><td><code>tag</code></td><td>Gives a tag (identified by the given address) that applies to the current document.</td><td>Not allowed</td><td>Link</td><td>Not allowed</td></tr></tbody></table>

The `rel` attribute is relevant to the [`<link>`](../element/link), [`<a>`](../element/a), [`<area>`](../element/area), and [`<form>`](../element/form) elements, but some values only relevant to a subset of those elements. Like all HTML keyword attribute values, these values are case-insenstive.

The `rel` attribute has no default value. If the attribute is omitted or if none of the values in the attribute are supported, then the document has no particular relationship with the destination resource other than there being a hyperlink between the two. In this case, on [`<link>`](../element/link) and [`<form>`](../element/form), if the `rel` attribute is absent, has no keywords, or if not one or more of the space-separated keywords above, then the element does not create any links. [`<a>`](../element/a) and [`<area>`](../element/area) will still created links, but without a defined relationship.

Like all HTML keyword attribute values, these values are case-insensitive.

Values
------

If there are multiple `<link rel="icon">`s, the browser uses their [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/media) attribute, [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/type) and [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/sizes) attributes to select the most appropriate icon. If several icons are equally appropriate, the last one is used. If the most appropriate icon is later found to be inappropriate, for example, because it uses an unsupported format, the browser proceeds to the next-most appropriate, and so on.

**Note:** Apple's iOS does not use this link type, nor the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/sizes) attribute, like others mobile browsers do, to select a webpage icon for Web Clip or a start-up placeholder. Instead, it uses the non-standard [`apple-touch-icon`](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW4) and [`apple-touch-startup-image`](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW6) respectively.

The `shortcut` link type is often seen before `icon`, but this link type is non-conforming, ignored and **web authors must not use it anymore**.

`alternate`  
Indicates an alternate representation of the current document. Valid for link, a, and area, the meaning depends on the values of the other attributes.

-   With the `stylesheet` keyword on a `<link>`, it creates an alternate stylesheet.

        <!-- a persistent style sheet -->
        <link rel="stylesheet" href="default.css">
        <!-- alternate style sheets -->
        <link rel="alternate stylesheet" href="highcontrast.css" title="High contrast">

-   With an [hreflang](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/hreflang) attribute that differs from the document language, it indicates a translation.
-   With the [type](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/type) attribute, it indicates that the referenced document is the same content in a different format. For example, with `type="application/rss+xml"` it creates a hyperlink referencing a syndication feed.

        <link rel="alternate" type="application/atom+xml" href="posts.xml" title="Blog">

-   Both the [hreflang](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/hreflang) and [type](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/type) attributes specify links to versions of the document in an alternative format and language, intended for other media:

        <link rel=alternate href="/fr/html/print" hreflang=fr type=text/html media=print title="French HTML (for printing)">
        <link rel=alternate href="/fr/pdf" hreflang=fr type=application/pdf title="French PDF">

Note: The obsolete `rev="made"` is treated as `rel="alternate"`

`author`  
Indicates the author of the current document or article. Relevant for [`<link>`](../element/link), [`<a>`](../element/a), and [`<area>`](../element/area) elements, the `author` keyword creates a hyperlink. With [`<a>`](../element/a) and [`<area>`](../element/area), it indicates the linked document (or `mailto:`) provides information about the author of the nearest [`<article>`](../element/article) ancestor if there is one, otherwise the entire document. For [`<link>`](../element/link), it represents the author of the entire document.

`bookmark`  
Relevant as the `rel` attribute value for the [`<a>`](../element/a) and [`<area>`](../element/area) elements, the bookmark provides a permalink for ancestor section, which is the nearest ancestor [`<article>`](../element/article) or [`<section>`](../element/section), if there is at least one, otherwise, the nearest heading sibling or ancestor descendant, to the next..

`canonical`  
Valid for [`<link>`](../element/link), it defines the preferred URL for the current document, which is useful for search engines.

`dns-prefetch`  
Relevant for the [`<link>`](../element/link) element both in the [`<body>`](../element/body) and [`<head>`](../element/head), it tells the browser to preemptively perform DNS resolution for the target resource's origin. Useful for resources the user will likely need, it helps reduce latency and thereby improves performance when the user does access the resources as the browser preemptively performed DNS resolution for the origin of the specified resource. See [dns-prefetch](https://developer.mozilla.org/en-US/docs/Web/Performance/dns-prefetch) described in [resource hints](rel).

`external`  
Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and [`<area>`](../element/area), it indicates the referenced document is not part of the current site. This can be used with attribute selectors to style external links in a way that indicates to the user that they will be leaving the current site.

`help`  
Relevant to [`<form>`](../element/form), [`<link>`](../element/link), [`<a>`](../element/a), and [`<area>`](../element/area), the `help` keyword indicates that the linked to content provides context-sensitive help, providing information for the parent of the element defining the hyperlink, and its children. When used within `<link>`, the help is for the whole document. When included with [`<a>`](../element/a) and [`<area>`](../element/area) and supported, the default [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor) will be `help` instead of `pointer`.

`icon`  
Valid with [`<link>`](../element/link), the linked resource represents the icon, a resource for representing the page in the user interface, for the current document.

The most common use for the `icon` value is the favicon:

    <link rel="icon" href="favicon.ico">

If there are multiple `<link rel="icon">`s, the browser uses their [`media`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/media) attribute, [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/type), and [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/sizes) attributes to select the most appropriate icon. If several icons are equally appropriate, the last one is used. If the most appropriate icon is later found to be inappropriate, for example because it uses an unsupported format, the browser proceeds to the next-most appropriate, and so on.

Prior to Firefox 83 the [crossorigin](crossorigin) attribute was not supported for `rel="icon"` there is also [an open issue for Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=1121645).

**Note:** Apple's iOS does not use this link type, nor the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/sizes) attribute, like others mobile browsers do, to select a webpage icon for Web Clip or a start-up placeholder. Instead it uses the non-standard [`apple-touch-icon`](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW4) and [`apple-touch-startup-image`](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html#//apple_ref/doc/uid/TP40002051-CH3-SW6) respectively.

The `shortcut` link type is often seen before `icon`, but this link type is non-conforming, ignored and **web authors must not use it anymore**.

`license`  
Valid on the [`<a>`](../element/a), [`<area>`](../element/area), [`<form>`](../element/form), [`<link>`](../element/link) elements, the `license` value indicates that the hyperlink leads to a document describing the licensing information; that the main content of the current document is covered by the copyright license described by the referenced document. If not inside the [`<head>`](../element/head) element, the standard doesn't distinguish between a hyperlink applying to a specific part of the document or to the document as a whole. Only the data on the page can indicate this.

    <link rel="license" href="#license">

**Note:** Although recognized, the synonym `copyright` is incorrect and must be avoided.

`manifest`  
[Web app manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest). Requires the use of the CORS protocol for cross-origin fetching.

`modulepreload`  
Useful for improved performance, and relevant to the [`<link>`](../element/link) anywhere in the document, setting `rel="modulepreload"` tells the browser to preemptively fetch the script (and dependencies) and store it in the document's module map for later evaluation. `modulepreload` links can ensure network fetching is done with the module ready (but not evaluated) in the module map before it is necessarily needed. See also [link types: `modulepreload`](../link_types/modulepreload).

`next`  
Relevant to [`<form>`](../element/form), [`<link>`](../element/link), [`<a>`](../element/a), and [`<area>`](../element/area), the `next` values indicates that the current document is a part of a series, and that the next document in the series is the referenced document. When included in a `<link>`, browsers may assume that document will be fetched next, and treat it as a resource hint.

`nofollow`  
Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and [`<area>`](../element/area), the `nofollow` keyword tells search engine spiders to ignore the link relationship. The nofollow relationship may indicate the current document's owner does not endorse the referenced document. It is often included by Search Engine Optimizers pretending their link farms are not spam pages.

`noopener`  
Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and [`<area>`](../element/area), creates a top-level browsing context that is not an auxiliary browsing context if the hyperlink would create either of those to begin with (i.e., has an appropriate` target `attribute value). In other words, it makes the link behave as if `window.opener` were null and `target="_parent"` were set.  
  
This is the opposite of [opener](#opener).

`noreferrer`  
Relevant to [`<form>`](../element/form), [`<a>`](../element/a), and [`<area>`](../element/area), including this value makes the referrer unknown (no `Referer` header will be included), and creates a top-level browsing context as if `noopener` were also set.

`opener`  
Creates an auxiliary browsing context if the hyperlink would otherwise create a top-level browsing context that is not anauxiliary browsing context (i.e., has "`_blank`" as `target` attribute value). Effectively, the opposite of [noopener](#noopener).

`pingback`  
Gives the address of the pingback server that handles pingbacks to the current document.

`preconnect`  
Specifies that the user agent should preemptively connect to the target resource's origin.

`prefetch`  
Specifies that the user agent should preemptively fetch and cache the target resource as it is likely to be required for a followup navigation.

`preload`  
Specifies that the user agent must preemptively fetch and cache the target resource for current navigation according to the potential destination given by the `as` attribute (and the priority associated with the corresponding destination).

`prerender`  
Specifies that the user agent should preemptively fetch the target resource and process it in a way that helps deliver a faster response in the future.

`prev`  
Similar to the [next](#next) keyword, relevant to [`<form>`](../element/form), [`<link>`](../element/link), [`<a>`](../element/a), and [`<area>`](../element/area), the `prev` values indicates that the current document is a part of a series, and that the link references a previous document in the series is the referenced document.

Note: The synonym `previous` is incorrect and should not be used.

`search`  
Relevant to [`<form>`](../element/form), [`<link>`](../element/link), [`<a>`](../element/a), and [`<area>`](../element/area) elements, the `search` keywords indicates that the hyperlink references a document whose interface is specially designed for searching in the current document, site, and related resources, providing a link to a resource that can be used to search.

If the `type` attribute is set to `application/opensearchdescription+xml` the resource is an [OpenSearch](https://developer.mozilla.org/en-US/docs/Web/OpenSearch) plugin that can be easily added to the interface of some browsers like Firefox or Internet Explorer.

`stylesheet`  
Valid for the [`<link>`](../element/link) element, it imports an external resource to be used as a stylesheet. The `type` attribute is not needed as it's a `text/css` stylesheet, as that is the default value. If it's not a stylesheet of type `text/css` it is best to declare the type.

While this attribute defines the link as being a stylesheet, the interaction with other attributes and other key terms within the rel value impact whether the stylesheet is downloaded and/or used.

When used with the [alternate](#alternate) keyword, it defines an alternative style sheet. In this case, include a non-empty `title`.

The external stylesheet will not be used or even downloaded if the media does not match the value of the `media` attribute.

Requires the use of the CORS protocol for cross-origin fetching.

`tag`  
Valid for the [`<a>`](../element/a), and [`<area>`](../element/area) elements, it gives a tag (identified by the given address) that applies to the current document. The tag value denotes that the link refers to a document describing a tag applying to the document on which it is located. This link type is not meant for tags within a tag cloud, as those tags apply to a group of pages, whereas the `tag` value of the `rel` attribute is for a single document.

### Non-standard values

apple-touch-icon-precomposed  
     <!-- third-generation iPad with high-resolution Retina display: -->
      <link rel="apple-touch-icon-precomposed" sizes="144x144" href="/static/img/favicon144.e7e21ca263ca.png">
      <!-- iPhone with high-resolution Retina display: -->
      <link rel="apple-touch-icon-precomposed" sizes="114x114" href="/static/img/favicon114.d526f38b09c5.png">
      <!-- first- and second-generation iPad: -->
      <link rel="apple-touch-icon-precomposed" sizes="72x72" href="/static/img/favicon72.cc65d1d762a0.png">
      <!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
      <link rel="apple-touch-icon-precomposed" href="/static/img/favicon57.de33179910ae.png">
      <!-- basic favicon -->
      <link rel="shortcut icon" href="/static/img/favicon32.7f3da72dcea1.png">

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.rel`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

Specifications
--------------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/links.html#linkTypes">HTML Living Standard<br />
<span class="small">The definition of 'rel attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>opener</code>. Made <code>noopener</code> default for <code>target="_blank"</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/links.html#linkTypes">HTML5<br />
<span class="small">The definition of 'rel attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>tag</code>, <code>search</code>, <code>prefetch</code>, <code>noreferrer</code>, <code>nofollow</code>, <code>icon</code>, and <code>author</code>.<br />
Renamed <code>copyright</code> to <code>license</code>.<br />
Removed <code>start</code>, <code>chapter</code>, <code>section</code>, <code>subsection</code>, and <code>appendix</code></td></tr><tr class="odd"><td><a href="https://w3c.github.io/preload/#x2.link-type-preload">Preload<br />
<span class="small">The definition of 'preload' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added <code>preload</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/resource-hints/#dfn-preconnect">Resource Hints<br />
<span class="small">The definition of 'preconnect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <code>dns-prefetch</code>, <code>preconnect</code>, and <code>prerender</code> values.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/types.html#type-links">HTML 4.01 Specification<br />
<span class="small">The definition of 'link types' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>alternate</code>, <code>stylesheet</code>, <code>start</code>, <code>chapter</code>, <code>section</code>, <code>subsection</code>, <code>appendix</code>, and <code>bookmark</code>.<br />
Renamed <code>previous</code> to <code>prev</code>.<br />
Removed <code>top</code>, and <code>search</code>.</td></tr><tr class="even"><td><a href="about:unknown#link">Unknown<br />
<span class="small">The definition of '&lt;link&gt;' in that specification.</span></a></td><td><p><span class="spec-">Unknown</span><span class="spec-Obsolete"> (Obsolete)</span></p></td><td>Added <code>top</code>, <code>contents</code>, <code>index</code>, <code>glossary</code>, <code>copyright</code>, <code>next</code>, <code>previous</code>, <code>help</code>, and <code>search</code>.</td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc1866">RFC 1866: HTML 2.0</a></td><td><span class="spec-">Unknown</span><span class="spec-Obsolete">(Obsolete)</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

BCD tables only load in the browser

Accessibility concerns
----------------------

See also
--------

-   [`HTMLLinkElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/relList)
-   [`HTMLAnchorElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/relList)
-   [`HTMLAreaElement.relList`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/relList)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel</a>
