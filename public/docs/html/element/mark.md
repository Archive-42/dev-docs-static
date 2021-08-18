&lt;mark&gt;: The Mark Text element
===================================

The **HTML Mark Text element** (`<mark>`) represents text which is **marked** or **highlighted** for reference or notation purposes, due to the marked passage's relevance or importance in the enclosing context.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

Typical use cases for `<mark>` include:

-   When used in a quotation ([`<q>`](q)) or block quote ([`<blockquote>`](blockquote)), it generally indicates text which is of special interest but is not marked in the original source material, or material which needs special scrutiny even though the original author didn't think it was of particular importance. Think of this like using a highlighter pen in a book to mark passages that you find of interest.
-   Otherwise, `<mark>` indicates a portion of the document's content which is likely to be relevant to the user's current activity. This might be used, for example, to indicate the words that matched a search operation.
-   Don't use `<mark>` for syntax highlighting purposes; instead, use the [`<span>`](span) element with appropriate CSS applied to it.

Don't confuse `<mark>` with the [`<strong>`](strong) element; `<mark>` is used to denote content which has a degree of *relevance*, while `<strong>` indicates spans of text of *importance*.

Examples
--------

### Marking text of interest

In this first example, a `<mark>` element is used to mark some text within a quote which is of particular interest to the user.

    <blockquote>
      It is a period of civil war. Rebel spaceships, striking from a
      hidden base, have won their first victory against the evil
      Galactic Empire. During the battle, <mark>Rebel spies managed
      to steal secret plans</mark> to the Empire’s ultimate weapon,
      the DEATH STAR, an armored space station with enough power to
      destroy an entire planet.
    </blockquote>

The resulting output looks like this:

### Identifying context-sensitive passages

This example demonstrates using `<mark>` to mark search results within a passage.

    <p>It is a dark time for the Rebellion. Although the Death
    Star has been destroyed, <mark class="match">Imperial</mark>
    troops have driven the Rebel forces from their hidden base and
    pursued them across the galaxy.</p>

    <p>Evading the dreaded <mark class="match">Imperial</mark>
    Starfleet, a group of freedom fighters led by Luke Skywalker
    has established a new secret base on the remote ice world of
    Hoth.</p>

To help distinguish the use of `<mark>` for search results from other potential usage, this example applies the custom class `"match"` to each match.

The results look like this:

Accessibility concerns
----------------------

The presence of the `mark` element is not announced by most screen reading technology in its default configuration. It can be made to be announced by using the CSS [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property, along with the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) and [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-elements.

    mark::before,
    mark::after {
      clip-path: inset(100%);
      clip: rect(1px, 1px, 1px, 1px);
      height: 1px;
      overflow: hidden;
      position: absolute;
      white-space: nowrap;
      width: 1px;
    }

    mark::before {
      content: " [highlight start] ";
    }

    mark::after {
      content: " [highlight end] ";
    }

Some people who use screen readers deliberately disable announcing content that creates extra verbosity. Because of this, it is important to not abuse this technique and only apply it in situations where not knowing content has been highlighted would adversely affect understanding.

-   [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
-   [Tweaking Text Level Styles | Adrian Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-mark-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;mark&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-mark-element">HTML5<br />
<span class="small">The definition of '&lt;mark&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`mark`

Yes

12

4

9

11

Yes

Yes

Yes

4

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark</a>
