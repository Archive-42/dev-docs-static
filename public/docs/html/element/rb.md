&lt;rb&gt;: The Ruby Base element
=================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<rb>` is used to delimit the base text component of a [`<ruby>`](ruby) annotation, i.e. the text that is being annotated. One `<rb>` element should wrap each separate atomic segment of the base text.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>As a child of a <a href="ruby"><code>&lt;ruby&gt;</code></a> element.</td></tr><tr class="odd"><td>Tag omission</td><td>The end tag can be omitted if the element is immediately followed by an <a href="rt"><code>&lt;rt&gt;</code></a>, <a href="rtc"><code>&lt;rtc&gt;</code></a>, or <a href="rp"><code>&lt;rp&gt;</code></a> element or another <code>&lt;rb&gt;</code> element, or if there is no more content in the parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="ruby"><code>&lt;ruby&gt;</code></a> element.</td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Ruby annotations are for showing pronunciation of East Asian characters, like using Japanese furigana or Taiwanese bopomofo characters. The `<rb>` element is used to separate out each segment of the ruby base text.
-   Even though `<rb>` is not an empty element, it is common to just include the opening tag of each element in the source code, so that the ruby markup is less complex and easier to read. The browser can then fill in the full element in the rendered version.
-   You need to include one [`<rt>`](rt) element for each base segment/`<rb>` element that you want to annotate.

Examples
--------

In this example, we provide an annotation for the original character equivalent of "Kanji":

    <ruby>
      <rb>漢<rb>字
      <rp>(</rp><rt>kan<rt>ji<rp>)</rp>
    </ruby>

Note how we've included two `<rb>` elements, to delimit the two separate parts of the ruby base text. The annotation on the other hand is delimited by two [`<rt>`](rt) elements.

Note that we could also write this example with the two base text parts annotated completely separately. In this case we don't need to include `<rb>` elements:

    <ruby>
      漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
      字 <rp>(</rp><rt>ji</rt><rp>)</rp>
    </ruby>

The output looks like so:

The HTML above might look something like this when rendered by a browser *without* ruby support:

**Note**: See the article about the [`<ruby>`](ruby) element for further examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-rb-element">HTML5<br />
<span class="small">The definition of '&lt;rb&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`rb`

5

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

79

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

38

5

15

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

5

Safari has support for parsing the `rb` element, but not for rendering `rb` content as expected.

37

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

18

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

38

14

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

Yes

Safari has support for parsing the `rb` element, but not for rendering `rb` content as expected.

Yes

Blink has support for parsing the `rb` element, but not for rendering `rb` content as expected.

See also
--------

-   [`<ruby>`](ruby)
-   [`<rt>`](rt)
-   [`<rp>`](rp)
-   [`<rtc>`](rtc)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb</a>
