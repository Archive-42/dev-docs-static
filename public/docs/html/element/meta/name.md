Standard metadata names
=======================

The [`<meta>`](../meta) element can be used to provide document metadata in terms of name-value pairs, with the [`name`](../meta#attr-name) attribute giving the metadata name, and the [`content`](../meta#attr-content) attribute giving the value.

### Standard metadata names defined in the HTML specification

The HTML specification defines the following set of standard metadata names:

-   `application-name`: the name of the application running in the web page.

    **Note:**
    -   Browsers may use this to identify the application. It is different from the [`<title>`](../title) element, which usually contain the application name, but may also contain information like the document name or a status.
    -   Simple web pages shouldn't define an application-name.

-   `author`: the name of the document's author.
-   `description`: a short and accurate summary of the content of the page. Several browsers, like Firefox and Opera, use this as the default description of bookmarked pages.
-   `generator`: the identifier of the software that generated the page.
-   `keywords`: words relevant to the page's content separated by commas.
-   `referrer`: controls the HTTP [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header for to requests sent from the document:
    <table><caption>Values for the <code>content</code> attribute of <code>&lt;meta name="referrer"&gt;</code> </caption><tbody><tr class="odd"><td><code>no-referrer</code></td><td>Do not send a HTTP <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer"><code>Referer</code></a> header.</td></tr><tr class="even"><td><code>origin</code></td><td>Send the <a href="https://developer.mozilla.org/en-US/docs/Glossary/Origin">origin</a> of the document.</td></tr><tr class="odd"><td><code>no-referrer-when-downgrade</code></td><td>Send the full URL when the destination is at least as secure as the current page (HTTP(S)→HTTPS), but send no referrer when it's less secure (HTTPS→HTTP). This is the default behavior.</td></tr><tr class="even"><td><code>origin-when-cross-origin</code></td><td>Send the full URL (stripped of parameters) for same-origin requests, but only send the origin for other cases.</td></tr><tr class="odd"><td><code>same-origin</code></td><td>Send the full URL (stripped of parameters) for same-origin requests. Cross-origin requests will contain no referrer header.</td></tr><tr class="even"><td><code>strict-origin</code></td><td>Send the origin when the destination is at least as secure as the current page (HTTP(S)→HTTPS), but send no referrer when it's less secure (HTTPS→HTTP).</td></tr><tr class="odd"><td><code>strict-origin-when-cross-origin</code></td><td>Send the full URL (stripped of parameters) for same-origin requests. Send the origin when the destination is at least as secure as the current page (HTTP(S)→HTTPS). Otherwise, send no referrer.</td></tr><tr class="even"><td><code>unsafe-URL</code></td><td>Send the full URL (stripped of parameters) for same-origin or cross-origin requests.</td></tr></tbody></table>

    **Notes:**
    -   Dynamically inserting `<meta name="referrer">` (with [`document.write()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/write) or [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)) makes the referrer behavior unpredictable.
    -   When several conflicting policies are defined, the `no-referrer` policy is applied.

-   `theme-color`: indicates a suggested color that user agents should use to customize the display of the page or of the surrounding user interface. The `content` attribute contains a valid CSS [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value).
-   `color-scheme`: specifies one or more color schemes with which the document is compatible.

    The browser will use this information in tandem with the user's browser or device settings to determine what colors to use for everything from background and foregrounds to form controls and scrollbars. The primary use for `<meta name="color-scheme">` is to indicate compatibility with—and order of preference for—light and dark color modes.

    The value of the [`content`](../meta#attr-content) property for `color-scheme` may be one of the following:

    `normal`  
    The document is unaware of color schemes and should be rendered using the default color palette.

    \[`light` | `dark`\]+  
    One or more color schemes supported by the document. Specifying the same color scheme more than once has the same effect as specifying it only once. Indicating multiple color schemes indicates that the first scheme is preferred by the document, but that the second specified scheme is acceptable if the user prefers it.

    `only light`  
    Indicates that the document *only* supports light mode, with a light background and dark foreground colors. By specification, `only dark` *is not valid*, because forcing a document to render in dark mode when it isn't truly compatible with it can result in unreadable content; all major browsers default to light mode if not otherwise configured.

    For example, to indicate that a document prefers dark mode but does render functionally in light mode as well:

        <meta name="color-scheme" content="dark light">

    This works at the document level in the same way that the CSS [`color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme) property lets individual elements specify their preferred and accepted color schemes. Your styles can adapt to the current color scheme using the [`prefers-color-scheme`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme) CSS media feature.

### Standard metadata names defined in other specifications

The CSS Device Adaptation specification defines the following metadata name:

-   `viewport`: gives hints about the size of the initial size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport). Used by mobile devices only.

    <table><caption>Values for the content of <code>&lt;meta name="viewport"&gt;</code> </caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Value</th><th>Possible subvalues</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>width</code></td><td>A positive integer number, or the text <code>device-width</code></td><td>Defines the pixel width of the viewport that you want the web site to be rendered at.</td></tr><tr class="even"><td><code>height</code></td><td>A positive integer, or the text <code>device-height</code></td><td>Defines the height of the viewport. Not used by any browser.</td></tr><tr class="odd"><td><code>initial-scale</code></td><td>A positive number between <code>0.0</code> and <code>10.0</code></td><td>Defines the ratio between the device width (<code>device-width</code> in portrait mode or <code>device-height</code> in landscape mode) and the viewport size.</td></tr><tr class="even"><td><code>maximum-scale</code></td><td>A positive number between <code>0.0</code> and <code>10.0</code></td><td>Defines the maximum amount to zoom in. It must be greater or equal to the <code>minimum-scale</code> or the behavior is undefined. Browser settings can ignore this rule and iOS10+ ignores it by default.</td></tr><tr class="odd"><td><code>minimum-scale</code></td><td>A positive number between <code>0.0</code> and <code>10.0</code></td><td>Defines the minimum zoom level. It must be smaller or equal to the <code>maximum-scale</code> or the behavior is undefined. Browser settings can ignore this rule and iOS10+ ignores it by default.</td></tr><tr class="even"><td><code>user-scalable</code></td><td><code>yes</code> or <code>no</code></td><td>If set to <code>no</code>, the user is not able to zoom in the webpage. The default is <code>yes</code>. Browser settings can ignore this rule, and iOS10+ ignores it by default.</td></tr><tr class="odd"><td><code>viewport-fit</code></td><td><code>auto</code>, <code>contain</code> or <code>cover</code></td><td><p>The <code>auto</code> value doesn’t affect the initial layout viewport, and the whole web page is viewable.</p><p>The <code>contain</code> value means that the viewport is scaled to fit the largest rectangle inscribed within the display.</p><p>The <code>cover</code> value means that the viewport is scaled to fill the device display. It is highly recommended to make use of the <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/env()">safe area inset</a> variables to ensure that important content doesn't end up outside the display.</p></td></tr></tbody></table>

    **Notes:**
    -   Though unstandardized, this declaration is respected by most mobile browsers due to de-facto dominance.
    -   The default values may vary between devices and browsers.
    -   To learn about this declaration in Firefox for Mobile, see [this article](https://developer.mozilla.org/en-US/docs/Mobile/Viewport_meta_tag).

    ##### Accessibility concerns with viewport scaling

    Disabling zooming capabilities by setting `user-scalable` to a value of `no` prevents people experiencing low vision conditions from being able to read and understand page content.

    -   [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
    -   [Understanding Success Criterion 1.4.4 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

    ##### See also

    The [`@viewport`](https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport) CSS at-rule.

### Other metadata names

The [WHATWG Wiki MetaExtensions page](https://wiki.whatwg.org/wiki/MetaExtensions) contains a large set of non-standard metadata names that have not been formally accepted yet; however, some of the names included there are already used quite commonly in practice — including the following:

-   `creator`: the name of the creator of the document, such as an organization or institution. If there are more than one, several [`<meta>`](../meta) elements should be used.
-   `googlebot`, a synonym of `robots`, is only followed by Googlebot (the indexing crawler for Google).
-   `publisher`: the name of the document's publisher.
-   `robots`: the behavior that cooperative crawlers, or "robots", should use with the page. It is a comma-separated list of the values below:
    <table><caption>Values for the content of <code>&lt;meta name="robots"&gt;</code> </caption><thead><tr class="header"><th>Value</th><th>Description</th><th>Used by</th></tr></thead><tbody><tr class="odd"><td><code>index</code></td><td>Allows the robot to index the page (default).</td><td>All</td></tr><tr class="even"><td><code>noindex</code></td><td>Requests the robot to not index the page.</td><td>All</td></tr><tr class="odd"><td><code>follow</code></td><td>Allows the robot to follow the links on the page (default).</td><td>All</td></tr><tr class="even"><td><code>nofollow</code></td><td>Requests the robot to not follow the links on the page.</td><td>All</td></tr><tr class="odd"><td><code>all</code></td><td>Equivalent to <code>index, follow</code></td><td><a href="https://support.google.com/webmasters/answer/79812">Google</a></td></tr><tr class="even"><td><code>none</code></td><td>Equivalent to <code>noindex, nofollow</code></td><td><a href="https://support.google.com/webmasters/answer/79812">Google</a></td></tr><tr class="odd"><td><code>noarchive</code></td><td>Requests the search engine not to cache the page content.</td><td><a href="https://developers.google.com/webmasters/control-crawl-index/docs/robots_meta_tag#valid-indexing--serving-directives">Google</a>, <a href="https://help.yahoo.com/kb/search-for-desktop/SLN2213.html">Yahoo</a>, <a href="https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240">Bing</a></td></tr><tr class="even"><td><code>nosnippet</code></td><td>Prevents displaying any description of the page in search engine results.</td><td><a href="https://developers.google.com/webmasters/control-crawl-index/docs/robots_meta_tag#valid-indexing--serving-directives">Google</a>, <a href="https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240">Bing</a></td></tr><tr class="odd"><td><code>noimageindex</code></td><td>Requests this page not to appear as the referring page of an indexed image.</td><td><a href="https://developers.google.com/webmasters/control-crawl-index/docs/robots_meta_tag#valid-indexing--serving-directives">Google</a></td></tr><tr class="even"><td><code>nocache</code></td><td>Synonym of <code>noarchive</code>.</td><td><a href="https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240">Bing</a></td></tr></tbody></table>

    **Notes:**
    -   Only cooperative robots follow these rules. Do not expect to prevent e-mail harvesters with them.
    -   The robot still needs to access the page in order to read these rules. To prevent bandwidth consumption, use a *[robots.txt](https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt)* file.
    -   If you want to remove a page, `noindex` will work, but only after the robot visits the page again. Ensure that the `robots.txt` file is not preventing revisits.
    -   Some values are mutually exclusive, like `index` and `noindex`, or `follow` and `nofollow`. In these cases the robot's behavior is undefined and may vary between them.
    -   Some crawler robots, like Google, Yahoo and Bing, support the same values for the HTTP header `X-Robots-Tag`; this allows non-HTML documents like images to use these rules.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#standard-metadata-names">HTML Living Standard<br />
<span class="small">The definition of 'standard metadata names' in that specification.</span></a></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-device-adapt/#viewport-meta">CSS Device Adaptation<br />
<span class="small">The definition of 'the "viewport" metadata name' in that specification.</span></a></td></tr><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-meta">Referrer Policy<br />
<span class="small">The definition of 'the "referrer" metadata name' in that specification.</span></a></td></tr></tbody></table>

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

`name`

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

`color-scheme`

81

81

No

No

68

12.1

81

81

No

No

12.2

No

`referrer`

17

Until Chrome 46, `content` values weren't constrained to the values listed in the spec.

79

36

The `referrer` value wasn't taken into account when navigation was happening via the context menu or middle click until Firefox 39.

?

15

Until Opera 46, `content` values weren't constrained to the values listed in the spec.

?

37

Until Chrome 46, `content` values weren't constrained to the values listed in the spec.

18

Until Chrome 46, `content` values weren't constrained to the values listed in the spec.

36

The `referrer` value wasn't taken into account when navigation was happening via the context menu or middle click until Firefox 39.

?

?

1.0

Until Samsung Internet 5.0, `content` values weren't constrained to the values listed in the spec.

`scheme`

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

`theme-color`

73

Chrome uses the color only on installed progressive web apps.

39-72

Chrome reports support, but does not actually use the color anywhere.

79

Edge uses the color only on installed progressive web apps.

No

No

No

No

No

80

Chrome for Android does not use the color on devices with native dark mode enabled.

No

No

No

6.2

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name</a>
