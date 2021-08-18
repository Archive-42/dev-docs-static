&lt;hr&gt;: The Thematic Break (Horizontal Rule) element
========================================================

The `<hr>` represents a thematic break between paragraph-level elements: for example, a change of scene in a story, or a shift of topic within a section.

Historically, this has been presented as a horizontal rule or line. While it may still be displayed as a horizontal rule in visual browsers, this element is now defined in semantic terms, rather than presentational terms, so if you wish to draw a horizontal line, you should do so using appropriate CSS.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>It must have start tag, but must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>separator</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>presentation</code> or <code>none</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLHRElement"><code>HTMLHRElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Sets the alignment of the rule on the page. If no value is specified, the default value is `left`.

 `color` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Sets the color of the rule through color name or hexadecimal value.

 `noshade` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Sets the rule to have no shading.

 `size` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Sets the height, in pixels, of the rule.

 `width` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Sets the length of the rule on the page through a pixel or percentage value.

Example
-------

### HTML

    <p>
      This is the first paragraph of text.
      This is the first paragraph of text.
      This is the first paragraph of text.
      This is the first paragraph of text.
    </p>

    <hr>

    <p>
      This is the second paragraph of text.
      This is the second paragraph of text.
      This is the second paragraph of text.
      This is the second paragraph of text.
    </p>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-hr-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;hr&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Definition of the <code>&lt;hr&gt;</code> element</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-hr-element">HTML5<br />
<span class="small">The definition of '&lt;hr&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#h-15.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;hr&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <code>align</code>, <code>noshade</code>, <code>size</code>, and <code>width</code> attributes are deprecated</td></tr></tbody></table>

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

`hr`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`align`

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

`color`

33

12

1

≤6

20

10.1

4.4.3

33

4

20

10.3

2.0

`noshade`

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

`size`

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

See also
--------

-   [`<p>`](p)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr</a>
