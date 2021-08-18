&lt;rp&gt;: The Ruby Fallback Parenthesis element
=================================================

The `<rp>` is used to provide fall-back parentheses for browsers that do not support display of ruby annotations using the [`<ruby>`](ruby) element. One `<rp>` element should enclose each of the opening and closing parentheses that wrap the [`<rt>`](rt) element that contains the annotation's text.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Text</td></tr><tr class="odd"><td>Tag omission</td><td>The end tag can be omitted if the element is immediately followed by an <a href="rt"><code>&lt;rt&gt;</code></a> or another <code>&lt;rp&gt;</code> element, or if there is no more content in the parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="ruby"><code>&lt;ruby&gt;</code></a> element. <code>&lt;rp&gt;</code> must be positioned immediately before or after an <a href="rt"><code>&lt;rt&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Ruby annotations are for showing pronunciation of East Asian characters, like using Japanese furigana or Taiwanese bopomofo characters. The `<rp>` element is used in the case of lack of [`<ruby>`](ruby) element support; the `<rp>` content provides what should be displayed in order to indicate the presence of a ruby annotation, usually parentheses.

Examples
--------

This example uses ruby annotations to display the [Romaji](https://en.wikipedia.org/wiki/Romaji) equivalents for each character.

    <ruby>
      漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
      字 <rp>(</rp><rt>ji</rt><rp>)</rp>
    </ruby>

The result looks like this in your browser:

The HTML above rendered by a browser *without* ruby support might look like this:

See the article about the [`<ruby>`](ruby) element for further examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-rp-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;rp&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-rp-element">HTML5<br />
<span class="small">The definition of '&lt;rp&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`rp`

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
-   [`<rt>`](rt)
-   [`<rb>`](rb)
-   [`<rtc>`](rtc)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp</a>
