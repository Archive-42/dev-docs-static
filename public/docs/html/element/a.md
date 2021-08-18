&lt;a&gt;: The Anchor element
=============================

The `<a>` (or *anchor* element), with [its `href` attribute](#href), creates a hyperlink to web pages, files, email addresses, locations in the same page, or anything else a URL can address. Content within each `<a>` **should** indicate the link's destination. If [the `href` attribute](#href) is present, pressing the enter key while focused on the `<a>` element will activate it.

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`download`  
Prompts the user to save the linked URL instead of navigating to it. Can be used with or without a value:

-   Without a value, the browser will suggest a filename/extension, generated from various sources:
    -   The [`Content-Disposition`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition) HTTP header
    -   The final segment in the URL [path](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname)
    -   The [media type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) (from the [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header, the start of a [`data:` URL](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs), or [`Blob.type`](https://developer.mozilla.org/en-US/docs/Web/API/Blob/type) for a [`blob:` URL](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL))
-   Defining a value suggests it as the filename. `/` and `\` characters are converted to underscores (`_`). Filesystems may forbid other characters in filenames, so browsers will adjust the suggested name if necessary.

**Notes**
-   `download` only works for [same-origin URLs](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), or the `blob:` and `data:` schemes.
-   If the `Content-Disposition` header has different information from the `download` attribute, resulting behavior may differ:

    -   If the header specifies a `filename`, it takes priority over a filename specified in the `download` attribute.

    -   If the header specifies a disposition of `inline`, Chrome, and Firefox 82 and later, prioritize the attribute and treat it as a download. Firefox versions before 82 prioritize the header and will display the content inline.

`href`  
The URL that the hyperlink points to. Links are not restricted to HTTP-based URLs — they can use any URL scheme supported by browsers:

-   Sections of a page with fragment URLs
-   Pieces of media files with media fragments
-   Telephone numbers with `tel:` URLs
-   Email addresses with `mailto:` URLs
-   While web browsers may not support other URL schemes, web sites can with `registerProtocolHandler()`

`hreflang`  
Hints at the human language of the linked URL. No built-in functionality. Allowed values are the same as [the global `lang` attribute](../global_attributes/lang).

`ping`  
A space-separated list of URLs. When the link is followed, the browser will send [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) requests with the body `PING` to the URLs. Typically for tracking.

 `referrerpolicy`<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
How much of the [referrer](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) to send when following the link. See [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) for possible values and their effects.

`rel`  
The relationship of the linked URL as space-separated [link types](../link_types).

`target`  
Where to display the linked URL, as the name for a *browsing context* (a tab, window, or [`<iframe>`](iframe)). The following keywords have special meanings for where to load the URL:

-   `_self`: the current browsing context. (Default)
-   `_blank`: usually a new tab, but users can configure browsers to open a new window instead.
-   `_parent`: the parent browsing context of the current one. If no parent, behaves as `_self`.
-   `_top`: the topmost browsing context (the "highest" context that’s an ancestor of the current one). If no ancestors, behaves as `_self`.

**Note**
Setting `target="_blank"` on `<a>` elements implicitly provides the same `rel` behavior as setting `rel="noopener"` which does not set `window.opener`. See [browser compatibility](#browser_compatibility) for support status.

`type`  
Hints at the linked URL’s format with a [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type). No built-in functionality.

### Deprecated attributes

 `charset`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Hinted at the [character encoding](https://developer.mozilla.org/en-US/docs/Glossary/character_encoding) of the linked URL.

**Note**
This attribute is deprecated and **should not be used by authors**. Use the HTTP [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header on the linked URL.

 `coords`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Used with [the `shape` attribute](#shape). A comma-separated list of coordinates.

 `name`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Was required to define a possible target location in a page. In HTML 4.01, `id` and `name` could both be used on `<a>`, as long as they had identical values.

**Note**
Use the global attribute [`id`](../global_attributes#attr-id) instead.

 `rev`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specified a reverse link; the opposite of [the `rel` attribute](#rel). Deprecated for being very confusing.

 `shape`<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The shape of the hyperlink’s region in an image map.

**Note**
Use the [`<area>`](area) element for image maps instead.

Properties
----------

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">Transparent</a>, containing either <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a> (excluding <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a>) or <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, or any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, but not other <code>&lt;a&gt;</code> elements.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>link</code> when <code>href</code> attribute is present, otherwise <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><p>When <code>href</code> attribute is present:</p><ul><li><code>button</code></li><li><code>checkbox</code></li><li><code>menuitem</code></li><li><code>menuitemcheckbox</code></li><li><code>menuitemradio</code></li><li><code>option</code></li><li><code>radio</code></li><li><code>switch</code></li><li><code>tab</code></li><li><code>treeitem</code></li></ul><p>When <code>href</code> attribute is not present:</p><ul><li>any</li></ul></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement"><code>HTMLAnchorElement</code></a></td></tr></tbody></table>

Examples
--------

### Linking to an absolute URL

#### HTML

    <a href="https://www.mozilla.com">
      Mozilla
    </a>

#### Result

### Linking to relative URLs

#### HTML

    <a href="//example.com">Scheme-relative URL</a>
    <a href="/en-US/docs/Web/HTML">Origin-relative URL</a>
    <a href="./p">Directory-relative URL</a>

#### Result

### Linking to an element on the same page

    <!-- <a> element links to the section below -->
    <p><a href="#Section_further_down">
      Jump to the heading below
    </a></p>

    <!-- Heading to link to -->
    <h2 id="Section_further_down">Section further down</h2>

**Note**

You can use `href="#top"` or the empty fragment (`href="#"`) to link to the top of the current page, [as defined in the HTML specification](https://html.spec.whatwg.org/multipage/browsing-the-web.html#scroll-to-the-fragment-identifier).

### Linking to an email address

To create links that open in the user's email program to let them send a new message, use the `mailto:` scheme:

    <a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>

For details about `mailto:` URLs, such as including a subject or body, see [Email links](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks#e-mail_links) or [RFC 6068](https://tools.ietf.org/html/rfc6068).

### Linking to telephone numbers

    <a href="tel:+49.157.0156">+49 157 0156</a>
    <a href="tel:+1(555)5309">(555) 5309</a>

`tel:` link behavior varies with device capabilities:

-   Cellular devices autodial the number.
-   Most operating systems have programs that can make calls, like Skype or FaceTime.
-   Websites can make phone calls with [`registerProtocolHandler`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerProtocolHandler), such as `web.skype.com`.
-   Other behaviors include saving the number to contacts, or sending the number to another device.

See [RFC 3966](https://tools.ietf.org/html/rfc3966) for syntax, additional features, and other details about the `tel:` URL scheme.

### Using the download attribute to save a &lt;canvas&gt; as a PNG

To save a [`<canvas>`](canvas) element’s contents as an image, you can create a link with a `download` attribute and the canvas data as a `data:` URL:

#### Example painting app with save link

##### HTML

    <p>Paint by holding down the mouse button and moving it.
      <a href="" download="my_painting.png">Download my painting</a>
    </p>

    <canvas width="300" height="300"></canvas>

##### CSS

    html {
      font-family: sans-serif;
    }
    canvas {
      background: #fff;
      border: 1px dashed;
    }
    a {
      display: inline-block;
      background: #69c;
      color: #fff;
      padding: 5px 10px;
    }

##### JavaScript

    var canvas = document.querySelector('canvas'),
        c = canvas.getContext('2d');
    c.fillStyle = 'hotpink';

    function draw(x, y) {
      if (isDrawing) {
        c.beginPath();
        c.arc(x, y, 10, 0, Math.PI*2);
        c.closePath();
        c.fill();
      }
    }

    canvas.addEventListener('mousemove', event =>
      draw(event.offsetX, event.offsetY)
    );
    canvas.addEventListener('mousedown', () => isDrawing = true);
    canvas.addEventListener('mouseup', () => isDrawing = false);

    document.querySelector('a').addEventListener('click', event =>
      event.target.href = canvas.toDataURL()
    );

##### Result

Security and privacy
--------------------

`<a>` elements can have consequences for users’ security and privacy. See [`Referer` header: privacy and security concerns](https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns) for information.

Using `target="_blank"` without `rel="noreferrer"` and `rel="noopener"` makes the website vulnerable to [`window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener) API exploitation attacks ([vulnerability description](https://www.jitbit.com/alexblog/256-targetblank---the-most-underestimated-vulnerability-ever/)), although note that, in newer browser versions setting `target="_blank"` implicitly provides the same protection as setting `rel="noopener"`. See [browser compatibility](#browser_compatibility) for details.

Accessibility
-------------

### Strong link text

**The content inside a link should indicate where the link goes**, even out of context.

#### Inaccessible, weak link text

A sadly common mistake is to only link the words “click here” or “here”:

    <p>
      Learn more about our products <a href="/products">here</a>.
    </p>

#### Strong link text

Luckily, this is an easy fix, and it’s actually shorter than the inaccessible version!

    <p>
      Learn more <a href="/products">about our products</a>.
    </p>

Assistive software have shortcuts to list all links on a page. However, strong link text benefits all users — the “list all links” shortcut emulates how sighted users quickly scan pages.

### onclick events

Anchor elements are often abused as fake buttons by setting their `href` to `#` or `javascript:void(0)` to prevent the page from refreshing, then listening for their `click` events .

These bogus `href` values cause unexpected behavior when copying/dragging links, opening links in a new tab/window, bookmarking, or when JavaScript is loading, errors, or is disabled. They also convey incorrect semantics to assistive technologies, like screen readers.

Use a [`<button>`](button) instead. In general, **you should only use a hyperlink for navigation to a real URL**.

### External links and linking to non-HTML resources

Links that open in a new tab/window via `target="_blank"`, or links that point to a download file should indicate what will happen when the link is followed.

People experiencing low vision conditions, navigating with the aid of screen reading technology, or with cognitive concerns may be confused when a new tab, window, or application opens unexpectedly. Older screen-reading software may not even announce the behavior.

#### Link that opens a new tab/window

    <a target="_blank" href="https://www.wikipedia.org">
      Wikipedia (opens in new tab)
    </a>

#### Link to a non-HTML resource

    <a href="2017-annual-report.ppt">
      2017 Annual Report (PowerPoint)
    </a>

If an icon is used to signify link behavior, make sure it has [alt text](img#attr-alt):

    <a  target="_blank" href="https://www.wikipedia.org">
      Wikipedia
      <img alt="(opens in new tab)" src="newtab.svg">
    </a>

    <a href="2017-annual-report.ppt">
      2017 Annual Report
      <img alt="(PowerPoint file)" src="ppt-icon.svg">
    </a>

-   [WebAIM: Links and Hypertext - Hypertext Links](https://webaim.org/techniques/hypertext/hypertext_links)
-   [MDN / Understanding WCAG, Guideline 3.2](#)
-   [G200: Opening new windows and tabs from a link only when necessary](https://www.w3.org/TR/WCAG20-TECHS/G200.html)
-   [G201: Giving users advanced warning when opening a new window](https://www.w3.org/TR/WCAG20-TECHS/G201.html)

### Skip links

A **skip link** is a link placed as early as possible in [`<body>`](body) content that points to the beginning of the page's main content. Usually, CSS hides a skip link offscreen until focused.

    <body>
      <a href="#content">Skip to main content</a>

      <header>
        …
      </header>

      <main id="content"> <!-- The skip link jumps to here -->

    .skip-link {
      position: absolute;
      top: -3em;
      background: #fff;
    }
    .skip-link:focus {
      top: 0;
    }

Skip links let keyboard users bypass content repeated throughout multiple pages, such as header navigation.

Skip links are especially useful for people who navigate with the aid of assistive technology such as switch control, voice command, or mouth sticks/head wands, where the act of moving through repetitive links can be laborious.

-   [WebAIM: "Skip Navigation" Links](https://webaim.org/techniques/skipnav/)
-   [How-to: Use Skip Navigation links](https://a11yproject.com/posts/2013-05-11-skip-nav-links/)
-   [MDN / Understanding WCAG, Guideline 2.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.4_%e2%80%94_navigable_provide_ways_to_help_users_navigate_find_content_and_determine_where_they_are)
-   [Understanding Success Criterion 2.4.1](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

### Size and proximity

#### Size

Interactive elements, like links, should provide an area large enough that it is easy to activate them. This helps a variety of people, including those with motor control issues and those using imprecise inputs such as a touchscreen. A minimum size of 44×44 [CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

Text-only links in prose content are exempt from this requirement, but it’s still a good idea to make sure enough text is hyperlinked to be easily activated.

-   [Understanding Success Criterion 2.5.5: Target Size](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
-   [Target Size and 2.5.5](https://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
-   [Quick test: Large touch targets](https://a11yproject.com/posts/large-touch-targets/)

#### Proximity

Interactive elements, like links, placed in close visual proximity should have space separating them. Spacing helps people with motor control issues, who may otherwise accidentally activate the wrong interactive content.

Spacing may be created using CSS properties like [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin).

-   [Hand tremors and the giant-button-problem](https://axesslab.com/hand-tremors/)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrer attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerpolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/textlevel-semantics.html#the-a-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;a&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-a-element">HTML5<br />
<span class="small">The definition of '&lt;a&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/links.html#h-12.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;a&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`a`

Yes

12

Yes

Starting with Firefox 41, &lt;a&gt; without `href` attribute is no longer classified as interactive content: clicking it inside &lt;label&gt; will activate labelled content ([bug 1167816](https://bugzil.la/1167816)).

Yes

Yes

Yes

Yes

Yes

Yes

Starting with Firefox 41, &lt;a&gt; without `href` attribute is no longer classified as interactive content: clicking it inside &lt;label&gt; will activate labelled content ([bug 1167816](https://bugzil.la/1167816)).

Yes

Yes

Yes

`charset`

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

`coords`

No

No

Yes-58

You can no longer nest an `<a>` element inside a `<map>` element to create a hotspot region - `coords` and `shape` attribute support removed.

No

No

No

No

No

Yes-58

You can no longer nest an `<a>` element inside a `<map>` element to create a hotspot region - `coords` and `shape` attribute support removed.

No

No

No

`download`

14

Starting in Chrome 65, cross-origin downloads are not supported on the `<a>` element.

18

13

\["Until Edge 14 (build 14357), attempting to download data URIs caused Edge to crash ([bug 7160092](https://developer.microsoft.com/microsoft-edge/platform/issues/7160092/)).", "Edge 17 or older didn't follow the attributes' value to determine filename ([bug 7260192](https://developer.microsoft.com/microsoft-edge/platform/issues/7260192/))."\]

20

No

15

10.1

Yes

Starting in WebView 65, cross-origin downloads are not supported on the `<a>` element.

18

Starting in Chrome 65, cross-origin downloads are not supported on the `<a>` element.

20

?

13

1.0

Starting in Samsung Internet 9.0, cross-origin downloads are not supported on the `<a>` element.

`href`

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

`hreflang`

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

`implicit_noopener`

88

88

79

No

No

12.1

No

88

79

Yes

12.2

No

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

`ping`

12

17

Yes

No

15

6

≤37

18

Yes-79

14

6

1.0

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

`rev`

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

`shape`

No

No

Yes-58

You can no longer nest an `<a>` element inside a `<map>` element to create a hotspot region - `coords` and `shape` attribute support removed.

No

No

No

No

No

Yes-58

You can no longer nest an `<a>` element inside a `<map>` element to create a hotspot region - `coords` and `shape` attribute support removed.

No

No

No

`target`

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

`type`

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

-   [`<link>`](link) is similar to `<a>`, but for metadata hyperlinks that are invisible to users.
-   [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link) is a CSS pseudo-class that will match `<a>` elements with valid `href` attributes.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a</a>
