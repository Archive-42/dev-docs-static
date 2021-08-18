&lt;address&gt;: The Contact Address element
============================================

The contact information provided by an `<address>` element's contents can take whatever form is appropriate for the context, and may include any type of contact information that is needed, such as a physical address, URL, email address, phone number, social media handle, geographic coordinates, and so forth. The `<address>` element should include the name of the person, people, or organization to which the contact information refers.

`<address>` can be used in a variety of contexts, such as providing a business's contact information in the page header, or indicating the author of an article by including an `<address>` element within the [`<article>`](article).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, but with no nested <code>&lt;address&gt;</code> element, no heading content (<a href="hgroup"><code>&lt;hgroup&gt;</code></a>, <a href="heading_elements"><code>&lt;h1&gt;</code></a>, <a href="heading_elements"><code>&lt;h2&gt;</code></a>, <a href="heading_elements"><code>&lt;h3&gt;</code></a>, <a href="heading_elements"><code>&lt;h4&gt;</code></a>, <a href="heading_elements"><code>&lt;h5&gt;</code></a>, <a href="heading_elements"><code>&lt;h6&gt;</code></a>), no sectioning content (<a href="article"><code>&lt;article&gt;</code></a>, <a href="aside"><code>&lt;aside&gt;</code></a>, <a href="section"><code>&lt;section&gt;</code></a>, <a href="nav"><code>&lt;nav&gt;</code></a>), and no <a href="header"><code>&lt;header&gt;</code></a> or <a href="footer"><code>&lt;footer&gt;</code></a> element.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, but always excluding <code>&lt;address&gt;</code> elements (according to the logical principle of symmetry, if <code>&lt;address&gt;</code> tag, as a parent, can not have nested <code>&lt;address&gt;</code> element, then the same <code>&lt;address&gt;</code> content can not have <code>&lt;address&gt;</code> tag as its parent).</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a> Prior to Gecko 2.0 (Firefox 4), Gecko implemented this element using the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a> interface</td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   It used to be the case that an `<address>` element was only supposed to be used to represent the contact information of the document's author. In the latest spec versions however, its definition has been updated so it can now be used to mark up arbitrary addresses.
-   This element should not contain more information than the contact information, like a publication date (which belongs in a [`<time>`](time) element).
-   Typically an `<address>` element can be placed inside the [`<footer>`](footer) element of the current section, if any.

Examples
--------

This example demonstrates the use of `<address>` to demarcate the contact information for an article's author.

      <address>
        You can contact author at <a href="http://www.somedomain.com/contact">
        www.somedomain.com</a>.<br>
        If you see any bugs, please <a href="mailto:webmaster@somedomain.com">
        contact webmaster</a>.<br>
        You may also want to visit us:<br>
        Mozilla Foundation<br>
        331 E Evelyn Ave<br>
        Mountain View, CA 94041<br>
        USA
      </address>

### Result

Although it renders text with the same default styling as the [`<i>`](i) or [`<em>`](em) elements, it is more appropriate to use `<address>` when dealing with contact information, as it conveys additional semantic information.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/sections.html#the-address-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;address&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-address-element">HTML5<br />
<span class="small">The definition of '&lt;address&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.5.6">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;address&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`address`

Yes

12

1

Yes

Yes

1

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Others section-related elements: [`<body>`](body), [`<nav>`](nav), [`<article>`](article), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<footer>`](footer), [`<section>`](section), [`<header>`](header);
-   <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines" class="deki-ns current">Sections and outlines of an HTML5 document</a>.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address</a>
