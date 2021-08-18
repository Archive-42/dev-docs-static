&lt;embed&gt;: The Embed External Content element
=================================================

The `<embed>` embeds external content at the specified point in the document. This content is provided by an external application or other source of interactive content such as a browser plug-in.

**Note:** This topic documents only the element that is defined as part of HTML5. It does not address earlier, non-standardized implementation of the element.

Keep in mind that most modern browsers have deprecated and removed support for browser plug-ins, so relying upon `<embed>` is generally not wise if you want your site to be operable on the average user's browser.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, embedded content, interactive content, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag, and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts embedded content.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>application</code>, <code>document</code>, <code>img</code>, <code>none</code>, <code>presentation</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLEmbedElement"><code>HTMLEmbedElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`height`  
The displayed height of the resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). This must be an absolute value; percentages are *not* allowed.

`src`  
The URL of the resource being embedded.

`type`  
The [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) to use to select the plug-in to instantiate.

`width`  
The displayed width of the resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). This must be an absolute value; percentages are *not* allowed.

Usage notes
-----------

You can use the [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) property to adjust the positioning of the embedded object within the element's frame, and the [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) property to control how the object's size is adjusted to fit within the frame.

Examples
--------

    <embed type="video/quicktime" src="movie.mov" width="640" height="480" title="Title of my video">

Accessibility concerns
----------------------

Use the [`title` attribute](../global_attributes/title) on an `embed` element to label its content so that people navigating with assistive technology such as a screen reader can understand what it contains. The title's value should concisely describe the embedded content. Without a title, they may not be able to determine what its embedded content is. This context shift can be confusing and time-consuming, especially if the `embed` element contains interactive content like video or audio.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-embed-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;embed&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-embed-element">HTML5<br />
<span class="small">The definition of '&lt;embed&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`embed`

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

`align`

1

79

1

No

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

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

`height`

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

`src`

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

`type`

1

79

1

No

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`width`

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

**Note**: Prior to version 45, Firefox did not display content of HTML resource, but a generic message saying the content needs a plug-in (see [bug 730768](https://bugzilla.mozilla.org/show_bug.cgi?id=730768)).

See also
--------

-   Other elements that are used for embedding content of various types include [`<audio>`](audio), [`<canvas>`](canvas), [`<iframe>`](iframe), [`<img>`](img), `<math>`, [`<object>`](object), [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg), and [`<video>`](video).
-   Positioning and sizing the embedded content within its frame: [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) and [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed</a>
