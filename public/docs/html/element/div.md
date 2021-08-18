&lt;div&gt;: The Content Division element
=========================================

The **HTML Content Division element** (`<div>`) is the generic container for flow content. It has no effect on the content or layout until styled in some way using [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) (e.g. styling is directly applied to it, or some kind of layout model like [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) is applied to its parent element).

As a "pure" container, the `<div>` element does not inherently represent anything. Instead, it's used to group content so it can be easily styled using the [`class`](../global_attributes#attr-class) or [`id`](../global_attributes#attr-id) attributes, marking a section of a document as being written in a different language (using the [`lang`](../global_attributes#attr-lang) attribute), and so on.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.<br />
Or (in <a href="https://developer.mozilla.org/en-US/docs/Glossary/WHATWG">WHATWG</a> HTML): If the parent is a <a href="dl"><code>&lt;dl&gt;</code></a> element: one or more <a href="dt"><code>&lt;dt&gt;</code></a> elements followed by one or more <a href="dd"><code>&lt;dd&gt;</code></a> elements, optionally intermixed with <a href="script"><code>&lt;script&gt;</code></a> and <a href="template"><code>&lt;template&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.<br />
Or (in <a href="https://developer.mozilla.org/en-US/docs/Glossary/WHATWG">WHATWG</a> HTML): <a href="dl"><code>&lt;dl&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement"><code>HTMLDivElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

**Note:** The `align` attribute is obsolete; do not use it anymore. Instead, you should use CSS properties or techniques such as [CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) or [CSS Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox) to align and position `<div>` elements on the page.

Usage notes
-----------

-   The `<div>` element should be used only when no other semantic element (such as [`<article>`](article) or [`<nav>`](nav)) is appropriate.

Examples
--------

### A simple example

    <div>
      <p>Any kind of content here. Such as
      &lt;p&gt;, &lt;table&gt;. You name it!</p>
    </div> 

The result looks like this:

### A styled example

This example creates a shadowed box by applying a style to the `<div>` using CSS. Note the use of the [`class`](../global_attributes#attr-class) attribute on the `<div>` to apply the style named `"shadowbox"` to the element.

#### HTML

    <div class="shadowbox">
      <p>Here's a very interesting note displayed in a
      lovely shadowed box.</p>
    </div>

#### CSS

    .shadowbox {
      width: 15em;
      border: 1px solid #333;
      box-shadow: 8px 8px 5px #444;
      padding: 8px 12px;
      background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
    }

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/grouping-content.html#the-div-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;div&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No changes since the latest snapshot</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-div-element">HTML5<br />
<span class="small">The definition of '&lt;div&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Obsoleted <code>align</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.5.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;div&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`div`

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

`align`

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

-   Semantic sectioning elements: [`<section>`](section), [`<article>`](article), [`<nav>`](nav), [`<header>`](header), [`<footer>`](footer)
-   [`<span>`](span) element for styling of phrasing content

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div</a>
