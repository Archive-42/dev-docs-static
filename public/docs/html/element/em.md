&lt;em&gt;: The Emphasis element
================================

The `<em>` marks text that has stress emphasis. The `<em>` element can be nested, with each level of nesting indicating a greater degree of emphasis.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a> Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement"><code>HTMLSpanElement</code></a> interface for this element.</td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<em>` element is for words that have a stressed emphasis compared to surrounding text, which is often limited to a word or words of a sentence and affects the meaning of the sentence itself.

Typically this element is displayed in italic type. However, it should not be used to apply italic styling; use the CSS [`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) property for that purpose. Use the [`<cite>`](cite) element to mark the title of a work (book, play, song, etc.). Use the [`<i>`](i) element to mark text that is in an alternate tone or mood, which covers many common situations for italics such as scientific names or words in other languages. Use the [`<strong>`](strong) element to mark text that has greater importance than surrounding text.

### &lt;i&gt; vs. &lt;em&gt;

New developers are often confused at seeing multiple elements that produce similar results. `<em>` and `<i>` are a common example, since they both italicize text. What's the difference? Which should you use?

By default, the visual result is the same. However, the semantic meaning is different. The `<em>` element represents stress emphasis of its contents, while the `<i>` element represents text that is set off from the normal prose, such a foreign word, fictional character thoughts, or when the text refers to the definition of a word instead of representing its semantic meaning. (The title of a work, such as the name of a book or movie, should use `<cite>`.)

This means the right one to use depends on the situation. Neither is for purely decorative purposes, that's what CSS styling is for.

An example for `<em>` could be: "Just *do* it already!", or: "We *had* to do something about it". A person or software reading the text would pronounce the words in italics with an emphasis, using verbal stress.

An example for `<i>` could be: "The *Queen Mary* sailed last night". Here, there is no added emphasis or importance on the word "Queen Mary". It is merely indicated that the object in question is not a queen named Mary, but a ship named *Queen Mary*. Another example for `<i>` could be: "The word *the* is an article".

Example
-------

The `<em>` element is often used to indicate an implicit or explicit contrast.

    <p>
      In HTML 5, what was previously called
      <em>block-level</em> content is now called
      <em>flow</em> content.
    </p>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-em-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;em&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-em-element">HTML5<br />
<span class="small">The definition of '&lt;em&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;em&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`em`

1

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

-   [`<i>`](i)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em</a>
