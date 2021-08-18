&lt;map&gt;
===========

The `<map>` is used with [`<area>`](area) elements to define an image map (a clickable link area).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>Any <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">transparent</a> element.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMapElement"><code>HTMLMapElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`name`  
The `name` attribute gives the map a name so that it can be referenced. The attribute must be present and must have a non-empty value with no space characters. The value of the `name` attribute must not be a compatibility-caseless match for the value of the `name` attribute of another `<map>` element in the same document. If the [`id`](../global_attributes#attr-id) attribute is also specified, both attributes must have the same value.

Examples
--------

    <map name="primary">
      <area shape="circle" coords="75,75,75" href="left.html">
      <area shape="circle" coords="275,75,75" href="right.html">
    </map>
    <img usemap="#primary" src="https://via.placeholder.com/350x150" alt="350 x 150 pic">

### Result

### Expected live example output

The live example above should appear similar to the following images (when using your keyboard tab key):

*For the `left.html` link:*  
<img src="data:image/png;base64,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" width="356" height="156" />

*For the `right.html` link*  
<img src="data:image/png;base64,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" width="355" height="157" />

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-map-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;map&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-map-element">HTML5<br />
<span class="small">The definition of '&lt;map&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.6.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;map&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`map`

1

12

1

\["Before Firefox 5, in Quirks Mode, empty maps were no longer skipped over in favor of non-empty ones when matching.", "Before Firefox 17, the default styling of the `<map>` HTML element was `display: block;`. This is now `display: inline;` and matches the behavior of the other browsers. It was already the case in Quirks Mode."\]

Yes

Yes

1

1

18

4

Yes

Yes

1.0

`name`

1

12

1

Yes

Yes

1

1

18

4

Yes

Yes

1.0

See also
--------

-   [`<a>`](a)
-   [`<area>`](area)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/map</a>
