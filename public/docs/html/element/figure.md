&lt;figure&gt;: The Figure with Optional Caption element
========================================================

The `<figure>` represents self-contained content, potentially with an optional caption, which is specified using the [`<figcaption>`](figcaption) element. The figure, its caption, and its contents are referenced as a single unit.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_roots">sectioning root</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>A <a href="figcaption"><code>&lt;figcaption&gt;</code></a> element, followed by <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>; or flow content followed by a <a href="figcaption"><code>&lt;figcaption&gt;</code></a> element; or flow content.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Figure_Role">figure</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>With no <a href="figcaption">figcaption</a> descendant: <a href="https://www.w3.org/TR/html-aria/#dfn-any-role">any</a>, otherwise no permitted roles</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   Usually a `<figure>` is an image, illustration, diagram, code snippet, etc., that is referenced in the main flow of a document, but that can be moved to another part of the document or to an appendix without affecting the main flow.
-   Being a [sectioning root](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_roots), the outline of the content of the `<figure>` element is excluded from the main outline of the document.
-   A caption can be associated with the `<figure>` element by inserting a [`<figcaption>`](figcaption) inside it (as the first or the last child). The first `<figcaption>` element found in the figure is presented as the figure's caption.

Examples
--------

### Images

    <!-- Just an image -->
    <figure>
      <img
      src="https://developer.mozilla.org/static/img/favicon144.png"
      alt="The beautiful MDN logo.">
    </figure>

    <!-- Image with a caption -->
    <figure>
      <img
      src="https://developer.mozilla.org/static/img/favicon144.png"
      alt="The beautiful MDN logo.">
      <figcaption>MDN Logo</figcaption>
    </figure>

### Code snippets

    <figure>
      <figcaption>Get browser details using <code>navigator</code>.</figcaption>
      <pre>
    function NavigatorExample() {
      var txt;
      txt = "Browser CodeName: " + navigator.appCodeName + "; ";
      txt+= "Browser Name: " + navigator.appName + "; ";
      txt+= "Browser Version: " + navigator.appVersion  + "; ";
      txt+= "Cookies Enabled: " + navigator.cookieEnabled  + "; ";
      txt+= "Platform: " + navigator.platform  + "; ";
      txt+= "User-agent header: " + navigator.userAgent  + "; ";
      console.log("NavigatorExample", txt);
    }
      </pre>
    </figure>

### Quotations

    <figure>
      <figcaption><cite>Edsger Dijkstra:</cite></figcaption>
      <blockquote>If debugging is the process of removing software bugs,
      then programming must be the process of putting them in.</blockquote>
    </figure>

### Poems

    <figure>
      <p style="white-space:pre">
    Bid me discourse, I will enchant thine ear,
      Or like a fairy trip upon the green,
    Or, like a nymph, with long dishevell'd hair,
      Dance on the sands, and yet no footing seen:
    Love is a spirit all compact of fire,
      Not gross to sink, but light, and will aspire.</p>
      <figcaption><cite>Venus and Adonis</cite>,
        by William Shakespeare</figcaption>
    </figure>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-figure-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;figure&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-figure-element">HTML 5.2<br />
<span class="small">The definition of '&lt;figure&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No changes from HTML 5.0.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-figure-element">HTML5<br />
<span class="small">The definition of '&lt;figure&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`figure`

8

12

4

9

11

5.1

Yes

Yes

4

11

5.1

Yes

See also
--------

-   The [`<figcaption>`](figcaption) element.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure</a>
