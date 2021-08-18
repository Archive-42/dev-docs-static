&lt;small&gt;: the side comment element
=======================================

The `<small>` **element** represents side-comments and small print, like copyright and legal text, independent of its styled presentation. By default, it renders text within it one font-size smaller, such as from `small` to `x-small`.

<table><tbody><tr class="odd"><td>Content categories</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a></td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a></td></tr><tr class="odd"><td>Tag omission</td><td>None, must have both a start tag and an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, or any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

### Basic usage

    <p>This is the first sentence.
     <small>This whole sentence is in small letters.</small>
    </p>

### CSS alternative

    <p>This is the first sentence.
      <span style="font-size:0.8em">This whole sentence is in small
      letters.</span>
    </p>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-small-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;small&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-small-element">HTML5<br />
<span class="small">The definition of '&lt;small&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/graphics.html#edef-SMALL">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;small&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Notes
-----

Although the `<small>` element, like the [`<b>`](b) and [`<i>`](i) elements, may be perceived to violate the principle of separation between structure and presentation, all three are valid in HTML5. Authors are encouraged to use their best judgement when determining whether to use `<small>` or CSS.

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

`small`

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

See also
--------

-   [`<b>`](b)
-   [`<sub>`](sub) and [`<sup>`](sup)
-   [`<font>`](font)
-   [`<style>`](style)
-   HTML 4.01 Specification: [Font Styles](https://www.w3.org/TR/html4/present/graphics.html#h-15.2)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small</a>
