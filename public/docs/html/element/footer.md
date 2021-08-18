&lt;footer&gt;
==============

The `<footer>` represents a footer for its nearest [sectioning content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content) or [sectioning root](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_root) element. A `<footer>` typically contains information about the author of the section, copyright data or links to related documents.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, but with no <code>&lt;footer&gt;</code> or <a href="header"><code>&lt;header&gt;</code></a> descendants.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>. Note that a <code>&lt;footer&gt;</code> element must not be a descendant of an <a href="address"><code>&lt;address&gt;</code></a>, <a href="header"><code>&lt;header&gt;</code></a> or another <code>&lt;footer&gt;</code> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Contentinfo_role">contentinfo</a>, or <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a> if a descendant of an <a href="article">article</a>, <a href="aside">aside</a>, <a href="main">main</a>, <a href="nav">nav</a> or <a href="section">section</a> element, or an element with <code>role=article</code>, <a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Complementary_role">complementary</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Main_role">main</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Navigation_Role">navigation</a> or <a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Region_role">region</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>group</code>, <code>presentation</code> or <code>none</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Enclose information about the author in an [`<address>`](address) element that can be included into the `<footer>` element.
-   The `<footer>` element is not sectioning content and therefore doesn't introduce a new section in the [outline](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines).

Examples
--------

    <footer>
      Some copyright info or perhaps some author
      info for an &lt;article&gt;?
    </footer>

Accessibility concerns
----------------------

Prior to the release of Safari 13, the `contentinfo` [landmark role](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signpostslandmarks) was not properly exposed by [VoiceOver](https://help.apple.com/voiceover/info/guide/). If needing to support legacy Safari browsers, add `role="contentinfo"` to the `footer` element to ensure the landmark will be properly exposed.

-   Related: [WebKit Bugzilla: 146930 – AX: HTML native elements (header, footer, main, aside, nav) should work the same as ARIA landmarks, sometimes they don't](https://bugs.webkit.org/show_bug.cgi?id=146930)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-footer-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;footer&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-footer-element">HTML5<br />
<span class="small">The definition of '&lt;footer&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`footer`

5

12

4

9

11.1

5

Yes

Yes

4

11.1

4.2

Yes

See also
--------

-   Other section-related elements: [`<body>`](body), [`<nav>`](nav), [`<article>`](article), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header), [`<section>`](section), [`<address>`](address);
-   [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)
-   [ARIA: Contentinfo role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Contentinfo_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer</a>
