&lt;data&gt;
============

The `<data>` links a given piece of content with a machine-readable translation. If the content is time- or date-related, the [`<time>`](time) element must be used.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement"><code>HTMLDataElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

`value`  
This attribute specifies the machine-readable translation of the content of the element.

Examples
--------

The following example displays product names but also associates each name with a product number.

    <p>New Products</p>
    <ul>
     <li><data value="398">Mini Ketchup</data></li>
     <li><data value="399">Jumbo Ketchup</data></li>
     <li><data value="400">Mega Jumbo Ketchup</data></li>
    </ul>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-data-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;data&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-data-element">HTML5<br />
<span class="small">The definition of '&lt;data&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`data`

62

≤18

22

No

49

10

62

62

22

46

10

8.0

See also
--------

-   The HTML [`<time>`](time) element.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/data</a>
