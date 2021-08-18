&lt;rt&gt;: The Ruby Text element
=================================

The `<rt>` specifies the ruby text component of a ruby annotation, which is used to provide pronunciation, translation, or transliteration information for East Asian typography. The `<rt>` element must always be contained within a [`<ruby>`](ruby) element.

See the article about the [`<ruby>`](ruby) element for more examples.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The end tag may be omitted if the <code>&lt;rt&gt;</code> element is immediately followed by an <code>&lt;rt&gt;</code> or <a href="rp"><code>&lt;rp&gt;</code></a> element, or if there is no more content in the parent element</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="ruby"><code>&lt;ruby&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

This simple example provides Romaji transliteration for the kanji characters within the [`<ruby>`](ruby) element:

    <ruby>
      漢 <rt>Kan</rt>
      字 <rt>ji</rt>
    </ruby>

The output looks like this in your browser:

On a browser *without* ruby support, this example might look like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-rt-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;rt&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-rt-element">HTML5<br />
<span class="small">The definition of '&lt;rt&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`rt`

5

79

38

5

15

5

Yes

Yes

38

14

Yes

Yes

See also
--------

-   [`<ruby>`](ruby)
-   [`<rp>`](rp)
-   [`<rb>`](rb)
-   [`<rtc>`](rtc)
-   [`text-transform: full-size-kana`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt</a>
