&lt;noscript&gt;
================

The `<noscript>` defines a section of HTML to be inserted if a script type on the page is unsupported or if scripting is currently turned off in the browser.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>When scripting is disabled and when it is a descendant of the <a href="head"><code>&lt;head&gt;</code></a> element: in any order, zero or more <a href="link"><code>&lt;link&gt;</code></a> elements, zero or more <a href="style"><code>&lt;style&gt;</code></a> elements, and zero or more <a href="meta"><code>&lt;meta&gt;</code></a> elements.<br />
When scripting is disabled and when it isn't a descendant of the <a href="head"><code>&lt;head&gt;</code></a> element: any <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">transparent content</a>, but no <code>&lt;noscript&gt;</code> element must be among its descendants.<br />
Otherwise: flow content or phrasing content.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, if there are no ancestor <code>&lt;noscript&gt;</code> element, or in a <a href="head"><code>&lt;head&gt;</code></a> element (but only for an HTML document), here again if there are no ancestor <code>&lt;noscript&gt;</code> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

    <noscript>
      <!-- anchor linking to external file -->
      <a href="https://www.mozilla.com/">External Link</a>
    </noscript>
    <p>Rocks!</p>

### Result with scripting enabled

Rocks!

### Result with scripting disabled

[External Link](https://www.mozilla.com/)

Rocks!

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#the-noscript-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;noscript&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-scripting.html#the-noscript-element">HTML5<br />
<span class="small">The definition of '&lt;noscript&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/scripts.html#h-18.3.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;noscript&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`noscript`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript</a>
