&lt;sup&gt;: The Superscript element
====================================

The **HTML Superscript element** (`<sup>`) specifies inline text which is to be displayed as superscript for solely typographical reasons. Superscripts are usually rendered with a raised baseline using smaller text.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<sup>` element should only be used for typographical reasons—that is, to change the position of the text to comply with typographical conventions or standards, rather than solely for presentation or appearance purposes.

For example, to style the [wordmark](https://en.wikipedia.org/wiki/Wordmark) of a business or product which uses a raised baseline should be done using CSS (most likely [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)) rather than `<sup>`. This would be done using, for example, `vertical-align: super` or, to shift the baseline up 50%, `vertical-align: 50%`.

Appropriate use cases for `<sup>` include (but aren't necessarily limited to):

-   Displaying exponents, such as "x<sup>3</sup>." It may be worth considering the use of [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) for these, especially in more complex cases. See [Exponents](#exponents) under [Examples](#examples) below.
-   Displaying [superior lettering](https://en.wikipedia.org/wiki/Superior_letter), which is used in some languages when rendering certain abbreviations. For example, in French, the word "mademoiselle" can be abbreviated "M<sup>lle</sup>"); this is an acceptable use case. See [Superior lettering](#superior_lettering) for examples.
-   Representing ordinal numbers, such as "4<sup>th</sup>" instead of "fourth." See [Ordinal numbers](#ordinal_numbers) for examples.

Examples
--------

### Exponents

Exponents, or powers of a number, are among the most common uses of superscripted text. For example:

    <p>One of the most common equations in all of physics is
    <var>E</var>=<var>m</var><var>c</var><sup>2</sup>.<p>

The resulting output looks like this:

### Superior lettering

Superior lettering is not technically the same thing as superscript. However, it is common to use `<sup>` to present superior lettering in HTML. Among the most common uses of superior lettering is the presentation of certain abbreviations in French:

    <p>Robert a présenté son rapport à M<sup>lle</sup> Bernard.</p>

The resulting output:

### Ordinal numbers

Ordinal numbers, such as "fourth" in English or "quinto" in Spanish may be abbreviated using numerals and language-specific text rendered in superscript:

    <p>The ordinal number "fifth" can be abbreviated in various
    languages as follows:</p>
    <ul>
      <li>English: 5<sup>th</sup></li>
      <li>French: 5<sup>ème</sup></li>
    </ul>

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

`sup`

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

-   The [`<sub>`](sub) HTML element that produces subscripts. Note that you cannot use them both at the same time and you need to use [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) to produce both a superscript and a subscript next to the chemical symbol of an element, representing its atomic number and its nuclear number.
-   The [`<msub>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msub), [`<msup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msup), and [`<msubsup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msubsup) MathML elements.
-   The CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup</a>
