&lt;header&gt;
==============

The `<header>` represents introductory content, typically a group of introductory or navigational aids. It may contain some heading elements but also a logo, a search form, an author name, and other elements.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, but with no <code>&lt;header&gt;</code> or <a href="footer"><code>&lt;footer&gt;</code></a> descendant.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>. Note that a <code>&lt;header&gt;</code> element must not be a descendant of an <a href="address"><code>&lt;address&gt;</code></a>, <a href="footer"><code>&lt;footer&gt;</code></a> or another <a href="header"><code>&lt;header&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Banner_role">banner</a>, or <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a> if a descendant of an <code>article</code>, <code>aside</code>, <code>main</code>, <code>nav</code> or <code>section</code> element, or an element with <code>role=article</code>, <code>complementary</code>, <code>main</code>, <code>navigation</code> or <code>region</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>group</code>, <code>presentation</code> or <code>none</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Usage notes
-----------

The `<header>` element is not sectioning content and therefore does not introduce a new section in the [outline](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines). That said, a `<header>` element is intended to usually contain the surrounding section's heading (an `h1`–`h6` element), but this is **not** required.

### Historical Usage

Although the `<header>` element didn't make its way into specifications until [HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5), it actually existed at the very beginning of HTML. As seen in [the very first website](http://info.cern.ch/), it was originally used as the `<head>` element. At some point, it was decided to use a different name. This allowed `<header>` to be free to fill a different role later on.

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

### Page Header

    <header>
      <h1>Main Page Title</h1>
      <img src="mdn-logo-sm.png" alt="MDN logo">
    </header>

### Article Header

    <article>
      <header>
        <h2>The Planet Earth</h2>
        <p>Posted on Wednesday, <time datetime="2017-10-04">4 October 2017</time> by Jane Smith</p>
      </header>
      <p>We live on a planet that's blue and green, with so many things still unseen.</p>
      <p><a href="https://janesmith.com/the-planet-earth/">Continue reading....</a></p>
    </article>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-header-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;header&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-header-element">HTML5<br />
<span class="small">The definition of '&lt;header&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`header`

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

-   Other section-related elements: [`<body>`](body), [`<nav>`](nav), [`<article>`](article), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<footer>`](footer), [`<section>`](section), [`<address>`](address).
-   [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header</a>
