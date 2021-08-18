&lt;param&gt;: The Object Parameter element
===========================================

The `<param>` defines parameters for an [`<object>`](object) element.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>As it is a void element, the start tag must be present and the end tag must not be present.</td></tr><tr class="even"><td>Permitted parents</td><td>An <a href="object"><code>&lt;object&gt;</code></a> before any <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement"><code>HTMLParamElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`name`  
Name of the parameter.

`value`  
Specifies the value of the parameter.

### Deprecated attributes

 `type` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Only used if the `valuetype` is set to `ref`. Specifies the MIME type of values found at the URI specified by value.

 `valuetype` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the type of the `value` attribute. Possible values are:

-   `data`: Default value. The value is passed to the object's implementation as a string.
-   `ref`: The value is a URI to a resource where run-time values are stored.
-   `object`: An ID of another [`<object>`](object) in the same document.

Examples
--------

Please see the [`<object>`](object) page for examples on `<param>`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-param-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;param&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-param-element">HTML5<br />
<span class="small">The definition of '&lt;param&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.3.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;param&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`param`

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

`name`

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

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`value`

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

`valuetype`

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

See also
--------

-   [`<object>`](object)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param</a>
