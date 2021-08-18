&lt;article&gt;: The Article Contents element
=============================================

The `<article>` represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable (e.g., in syndication). Examples include: a forum post, a magazine or newspaper article, or a blog entry, a product card, a user-submitted comment, an interactive widget or gadget, or any other independent item of content.

A given document can have multiple articles in it; for example, on a blog that shows the text of each article one after another as the reader scrolls, each post would be contained in an `<article>` element, possibly with one or more `<section>`s within.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content">sectioning content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a></td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>. Note that an <code>&lt;article&gt;</code> element must not be a descendant of an <a href="address"><code>&lt;address&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>article</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>application</code>, <code>document</code>, <code>feed</code>, <code>main</code>, <code>none</code>, <code>presentation</code>, <code>region</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Each `<article>` should be identified, typically by including a heading ([`<h1>`-`<h6>`](heading_elements) element) as a child of the `<article>` element.
-   When an `<article>` element is nested, the inner element represents an article related to the outer element. For example, the comments of a blog post can be `<article>` elements nested in the `<article>` representing the blog post.
-   Author information of an `<article>` element can be provided through the [`<address>`](address) element, but it doesn't apply to nested `<article>` elements.
-   The publication date and time of an `<article>` element can be described using the [`datetime`](time#attr-datetime) attribute of a [`<time>`](time) element. *Note that the [`pubdate`](time#attr-pubdate) attribute of [`<time>`](time) is no longer a part of the [W3C](https://developer.mozilla.org/en-US/docs/Glossary/W3C) [HTML5](https://developer.mozilla.org/en-US/docs/Glossary/HTML5) standard.*

Examples
--------

    <article class="film_review">
      <h2>Jurassic Park</h2>
      <section class="main_review">
        <h3>Review</h3>
        <p>Dinos were great!</p>
      </section>
      <section class="user_reviews">
        <h3>User reviews</h3>
        <article class="user_review">
          <h4>Too scary!</h4>
          <p>Way too scary for me.</p>
          <footer>
            <p>
              Posted on
              <time datetime="2015-05-16 19:00">May 16</time>
              by Lisa.
            </p>
          </footer>
        </article>
        <article class="user_review">
          <h4>Love the dinos!</h4>
          <p>I agree, dinos are my favorite.</p>
          <footer>
            <p>
              Posted on
              <time datetime="2015-05-17 19:00">May 17</time>
              by Tom.
            </p>
          </footer>
        </article>
      </section>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-15 19:00">May 15</time>
          by Staff.
        </p>
      </footer>
    </article>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-article-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;article&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sections.html#the-article-element">HTML 5.1<br />
<span class="small">The definition of '&lt;article&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sections.html#the-article-element">HTML5<br />
<span class="small">The definition of '&lt;article&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`article`

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

-   Other section-related elements: [`<body>`](body), [`<nav>`](nav), [`<section>`](section), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer), [`<address>`](address)
-   [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article</a>
