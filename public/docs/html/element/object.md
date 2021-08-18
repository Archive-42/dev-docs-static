&lt;object&gt;
==============

The `<object>` represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>; <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>; <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>, palpable content; if the element has a <a href="#attr-usemap"><code>usemap</code></a> attribute, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a>; <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_submittable">submittable</a> <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated</a> element.</td></tr><tr class="even"><td>Permitted content</td><td>zero or more <a href="param"><code>&lt;param&gt;</code></a> elements, then <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">transparent</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>application</code>, <code>document</code>, <code>image</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement"><code>HTMLObjectElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `archive` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A space-separated list of URIs for archives of resources for the object.

 `border` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The width of a border around the control, in pixels.

 `classid` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The URI of the object's implementation. It can be used together with, or in place of, the **data** attribute.

 `codebase` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The base path used to resolve relative URIs specified by **classid**, **data**, or **archive**. If not specified, the default is the base URI of the current document.

 `codetype` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The content type of the data specified by **classid**.

`data`  
The address of the resource as a valid URL. At least one of **data** and **type** must be defined.

 `declare` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The presence of this Boolean attribute makes this element a declaration only. The object must be instantiated by a subsequent `<object>` element. In HTML5, repeat the &lt;object&gt; element completely each time that the resource is reused.

`form`  
The form element, if any, that the object element is associated with (its *form owner*). The value of the attribute must be an ID of a [`<form>`](form) element in the same document.

`height`  
The height of the displayed resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). -- (Absolute values only. [NO percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))

`name`  
The name of valid browsing context (HTML5), or the name of the control (HTML 4).

 `standby` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A message that the browser can show while loading the object's implementation and data.

 `tabindex` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The position of the element in the tabbing navigation order for the current document.

`type`  
The [content type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the resource specified by **data**. At least one of **data** and **type** must be defined.

`usemap`  
A hash-name reference to a [`<map>`](map) element; that is a '\#' followed by the value of a [`name`](map#attr-name) of a map element.

`width`  
The width of the display resource, in [CSS pixels](https://drafts.csswg.org/css-values/#px). -- (Absolute values only. [NO percentages](https://html.spec.whatwg.org/multipage/embedded-content.html#dimension-attributes))

Examples
--------

### Embed a flash movie

    <!-- Embed a flash movie -->
    <object data="movie.swf"
      type="application/x-shockwave-flash"></object>

    <!-- Embed a flash movie with parameters -->
    <object data="movie.swf" type="application/x-shockwave-flash">
      <param name="foo" value="bar">
    </object>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-object-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;object&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-object-element">HTML5<br />
<span class="small">The definition of '&lt;object&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;object&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`object`

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

`archive`

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

`classid`

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

`codebase`

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

`codetype`

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

`data`

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

`declare`

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

`form`

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

`height`

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

`standby`

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

`usemap`

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

`width`

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

Note: Google Chrome doesn't support search for text (accessed via ctrl + F shortcut) inside `<object></object>` tags.

See also
--------

-   [`<applet>`](applet) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
-   [`<embed>`](embed)
-   [`<param>`](param)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object</a>
