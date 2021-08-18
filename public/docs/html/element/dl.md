&lt;dl&gt;: The Description List element
========================================

The `<dl>` element represents a description list. The element encloses a list of groups of terms (specified using the [`<dt>`](dt) element) and descriptions (provided by [`<dd>`](dd) elements). Common uses for this element are to implement a glossary or to display metadata (a list of key-value pairs).

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, and if the <code>&lt;dl&gt;</code> element's children include one name-value group, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><p>Either: Zero or more groups each consisting of one or more <a href="dt"><code>&lt;dt&gt;</code></a> elements followed by one or more <a href="dd"><code>&lt;dd&gt;</code></a> elements, optionally intermixed with <a href="script"><code>&lt;script&gt;</code></a> and <a href="template"><code>&lt;template&gt;</code></a> elements.<br />
Or: (in <a href="https://developer.mozilla.org/en-US/docs/Glossary/WHATWG">WHATWG</a> HTML, <a href="https://developer.mozilla.org/en-US/docs/Glossary/W3C">W3C</a> HTML 5.2 and later) One or more <a href="div"><code>&lt;div&gt;</code></a> elements, optionally intermixed with <a href="script"><code>&lt;script&gt;</code></a> and <a href="template"><code>&lt;template&gt;</code></a> elements.</p></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>group</code>, <code>list</code>, <code>none</code>, <code>presentation</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDListElement"><code>HTMLDListElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

### Single term and description

    <dl>
      <dt>Firefox</dt>
      <dd>
        A free, open source, cross-platform,
        graphical web browser developed by the
        Mozilla Corporation and hundreds of
        volunteers.
      </dd>

      <!-- Other terms and descriptions -->
    </dl>

### Multiple terms, single description

    <dl>
      <dt>Firefox</dt>
      <dt>Mozilla Firefox</dt>
      <dt>Fx</dt>
      <dd>
        A free, open source, cross-platform,
        graphical web browser developed by the
        Mozilla Corporation and hundreds of
        volunteers.
      </dd>

      <!-- Other terms and descriptions -->
    </dl>

### Single term, multiple descriptions

    <dl>
      <dt>Firefox</dt>
      <dd>
        A free, open source, cross-platform,
        graphical web browser developed by the
        Mozilla Corporation and hundreds of
        volunteers.
      </dd>
      <dd>
        The Red Panda also known as the Lesser
        Panda, Wah, Bear Cat or Firefox, is a
        mostly herbivorous mammal, slightly larger
        than a domestic cat (60 cm long).
      </dd>

      <!-- Other terms and descriptions -->
    </dl>

### Multiple terms and descriptions

It is also possible to define multiple terms with multiple corresponding descriptions, by combining the examples above.

### Metadata

Description lists are useful for displaying metadata as a list of key-value pairs.

    <dl>
      <dt>Name</dt>
      <dd>Godzilla</dd>
      <dt>Born</dt>
      <dd>1952</dd>
      <dt>Birthplace</dt>
      <dd>Japan</dd>
      <dt>Color</dt>
      <dd>Green</dd>
    </dl>

Tip: It can be handy to define a key-value separator in the CSS, such as:

    dt::after {
      content: ": ";
    }

### Wrapping name-value groups in `<div>` elements

[WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) HTML allows wrapping each name-value group in a [`<dl>`](dl) element in a [`<div>`](div) element. This can be useful when using [microdata](../microdata), or when [global attributes](../global_attributes) apply to a whole group, or for styling purposes.

    <dl>
      <div>
        <dt>Name</dt>
        <dd>Godzilla</dd>
      </div>
      <div>
        <dt>Born</dt>
        <dd>1952</dd>
      </div>
      <div>
        <dt>Birthplace</dt>
        <dd>Japan</dd>
      </div>
      <div>
        <dt>Color</dt>
        <dd>Green</dd>
      </div>
    </dl>

Notes
-----

Do not use this element (nor [`<ul>`](ul) elements) to merely create indentation on a page. Although it works, this is a bad practice and obscures the meaning of description lists.

To change the indentation of a description term, use the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property.

Accessibility concerns
----------------------

Each screen reader announces `<dl>` content differently. As of iOS 14, VoiceOver will announce that `<dl>` content is a list when navigating with the virtual cursor (not via the read-all command). Because of this, make sure each list item's content is written in such a way that it communicates its relationship to the other list items in the list grouping.

-   [CodePen - HTML Buddies: dt & dd](https://codepen.io/aardrian/debug/NzGaKP)
-   [VoiceOver on iOS 14 Supports Description Lists](https://adrianroselli.com/2020/09/voiceover-on-ios-14-supports-description-lists.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-dl-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;dl&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-dl-element">HTML 5.2<br />
<span class="small">The definition of '&lt;dl&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>It can now include <a href="div"><code>&lt;div&gt;</code></a> elements as children to wrap <code>&lt;dt&gt;</code> and <code>&lt;dd&gt;</code> elements.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/lists.html#h-10.3">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;dl&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`dl`

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

-   [`<dt>`](dt)
-   [`<dd>`](dd)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl</a>
