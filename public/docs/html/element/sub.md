&lt;sub&gt;: The Subscript element
==================================

The HTML **Subscript element** (`<sub>`) specifies inline text which should be displayed as subscript for solely typographical reasons. Subscripts are typically rendered with a lowered baseline using smaller text.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<sub>` element should be used only for typographical reasons—that is, to change the position of the text to comply with typographical conventions or standards, rather than solely for presentation or appearance purposes.

For example, using `<sub>` to style the name of a company which uses altered baselines in their [wordmark](https://en.wikipedia.org/wiki/Wordmark) would not be appropriate; instead, CSS should be used (likely the [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property, such as `vertical-align: sub` or, to more precisely control the baseline shift, `vertical-align: -25%`.

Appropriate use cases for `<sub>` include (but aren't necessarily limited to):

-   Marking up footnote numbers. See [Footnote numbers](#footnote_numbers) for an example.
-   Marking up the subscript in mathematical variable numbers (although you may also consider using a [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) formula for this). See [Variable subscripts](#variable_subscripts).
-   Denoting the number of atoms of a given element within a chemical formula (such as every developer's best friend, C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, otherwise known as "caffeine"). See [Chemical formulas](#chemical_formulas).

Examples
--------

### Footnote numbers

Traditional footnotes are denoted using numbers which are rendered in subscript. This is a common use case for `<sub>`:

    <p>According to the computations by Nakamura, Johnson, and
    Mason<sub>1</sub> this will result in the complete annihilation
    of both particles.</p>

The resulting output looks like this:

### Variable subscripts

In mathematics, families of variables related to the same concept (such as distances along the same axis) are represented using the same variable name with a subscript following. For example:

    <p>The horizontal coordinates' positions along the X-axis are
    represented as <var>x<sub>1</sub></var> ... <var>x<sub>n</sub></var>.</p>

The resulting output:

### Chemical formulas

When writing a chemical formula, such as H<sub>2</sub>0, the number of atoms of a given element within the described molecule is represented using a subscripted number; in the case of water, the subscripted "2" indicates that there are two atoms of hydrogen in the molecule.

Another example:

    <p>Almost every developer's favorite molecule is
    C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, which is
    commonly known as "caffeine."</p>

The output:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-sub-and-sup-elements">HTML Living Standard<br />
<span class="small">The definition of '&lt;sub&gt; and &lt;sup&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-sub-and-sup-elements">HTML5<br />
<span class="small">The definition of '&lt;sub&gt; and &lt;sup&gt;;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`sub`

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

-   The [`<sup>`](sup) HTML element that produces superscript. Note that you cannot use them both at the same time and you need to use [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) to produce both a superscript directly above a subscript next to the chemical symbol of an element, representing its atomic number and its nuclear number.
-   The [`<msub>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msub), [`<msup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msup), and [`<msubsup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msubsup) MathML elements.
-   The CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub</a>
