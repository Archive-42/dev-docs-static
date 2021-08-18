&lt;area&gt;
============

The `<area>` defines an area inside an image map that has predefined clickable areas. An image map allows geometric areas on an image to be associated with [hypertext link](https://developer.mozilla.org/en-US/docs/Glossary/Hyperlink).

This element is used only within a [`<map>`](map) element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>. The <code>&lt;area&gt;</code> element must have an ancestor <a href="map"><code>&lt;map&gt;</code></a>, but it need not be a direct parent.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>link</code> when <a href="#attr-href"><code>href</code></a> attribute is present, otherwise <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement"><code>HTMLAreaElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`alt`  
A text string alternative to display on browsers that do not display images. The text should be phrased so that it presents the user with the same kind of choice as the image would offer when displayed without the alternative text. This attribute is required only if the [`href`](#attr-href) attribute is used.

`coords`  
The `coords` attribute details the coordinates of the `shape` attribute in size, shape, and placement of an `<area>`.

-   `rect`: the value is `x1,y1,x2,y2`. Value specifies the coordinates of the top-left and bottom-right corner of the rectangle.  
    For example: `<area shape="rect" coords="0,0,253,27" href="#" target="_blank" alt="Mozilla">` The coords in the above example specify: 0,0 as the top-left corner and 253,27 as the bottom-right corner of the rectangle.
-   `circle`: the value is `x,y,radius`. Value specifies the coordinates of the circle center and the radius.  
    For example: `<area shape="circle" coords="130,136,60" href="#" target="_blank" alt="MDN">`
-   `poly`: the value is `x1,y1,x2,y2,..,xn,yn`. Value specifies the coordinates of the edges of the polygon. If the first and last coordinate pairs are not the same, the browser will add the last coordinate pair to close the polygon
-   `default`: defines the entire region

The values are numbers of CSS pixels.

`download`  
This attribute, if present, indicates that the author intends the hyperlink to be used for downloading a resource. See [`<a>`](a) for a full description of the [`download`](a#attr-download) attribute.

`href`  
The hyperlink target for the area. Its value is a valid URL. This attribute may be omitted; if so, the `<area>` element does not represent a hyperlink.

`hreflang`  
Indicates the language of the linked resource. Allowed values are determined by [BCP47](https://www.ietf.org/rfc/bcp/bcp47.txt). Use this attribute only if the [`href`](#attr-href) attribute is present.

`ping`  
Contains a space-separated list of URLs to which, when the hyperlink is followed, [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) requests with the body `PING` will be sent by the browser (in the background). Typically used for tracking.

 `referrerpolicy` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
A string indicating which referrer to use when fetching the resource:

-   "`no-referrer`" meaning that the `Referer:` header will not be sent.
-   "`no-referrer-when-downgrade`" meaning that no `Referer:` header will be sent when navigating to an origin without TLS (HTTPS). This is a user agent’s default behavior, if no policy is otherwise specified.
-   "`origin`" meaning that the referrer will be the origin of the page, that is roughly the scheme, the host and the port.
-   "`origin-when-cross-origin`" meaning that navigations to other origins will be limited to the scheme, the host and the port, while navigations on the same origin will include the referrer's path.
-   "`unsafe-url`" meaning that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe because it can leak origins and paths from TLS-protected resources to insecure origins.

`rel`  
For anchors containing the [`href`](#attr-href) attribute, this attribute specifies the relationship of the target object to the link object. The value is a space-separated list of [link types values](../link_types). The values and their semantics will be registered by some authority that might have meaning to the document author. The default relationship, if no other is given, is void. Use this attribute only if the [`href`](#attr-href) attribute is present.

`shape`  
The shape of the associated hot spot. The specifications for HTML defines the values `rect`, which defines a rectangular region; `circle`, which defines a circular region; `poly`, which defines a polygon; and `default`, which indicates the entire region beyond any defined shapes.

Many browsers, notably Internet Explorer 4 and higher, support `circ`, `polygon`, and `rectangle` as valid values for [`shape`](#attr-shape), but these values are non-standard.

`target`  
A keyword or author-defined name of the [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context) to display the linked resource.

The following keywords have special meanings:

-   `_self` (default): Show the resource in the current browsing context.
-   `_blank`: Show the resource in a new, unnamed browsing context.
-   `_parent`: Show the resource in the parent browsing context of the current one, if the current page is inside a frame. If there is no parent, acts the same as `_self`.
-   `_top`: Show the resource in the topmost browsing context (the browsing context that is an ancestor of the current one and has no parent). If there is no parent, acts the same as `_self`.

Use this attribute only if the [`href`](#attr-href) attribute is present.

**Note**
Setting `target="_blank"` on `<area>` elements implicitly provides the same `rel` behavior as setting `rel="noopener"` which does not set `window.opener`. See [browser compatibility](#browser_compatibility) for support status.

### Deprecated attributes

 `name` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Define a names for the clickable area so that it can be scripted by older browsers.

 `nohref` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Indicates that no hyperlink exists for the associated area.

**Note**
Since HTML5, omitting the `href` attribute is sufficient.

 `tabindex` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A numeric value specifying the position of the defined area in the browser tabbing order. This attribute is global in HTML5.

 `type` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
No effect. Browsers ignore it. (The W3C 5.3 fork of the HTML specification defines it as valid, but [the canonical HTML specification](https://html.spec.whatwg.org/multipage/#the-area-element) doesn’t, and it has no effect in any user agents.)

Examples
--------

    <map name="primary">
      <area shape="circle" coords="75,75,75" href="left.html" alt="Click to go Left">
      <area shape="circle" coords="275,75,75" href="right.html" alt="Click to go Right">
    </map>
    <img usemap="#primary" src="https://via.placeholder.com/350x150" alt="350 x 150 pic">

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerpolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>referrerpolicy</code> attribute.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-area-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;area&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-area-element">HTML5<br />
<span class="small">The definition of '&lt;area&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.6.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;area&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`area`

Yes

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

`accesskey`

Yes

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

`alt`

Yes

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

`coords`

Yes

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

`download`

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

`href`

Yes

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

`media`

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

`nohref`

Yes

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

`shape`

Yes

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

`tabindex`

Yes

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

`target`

Yes

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

Yes

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area</a>
