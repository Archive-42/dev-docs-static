&lt;style&gt;: The Style Information element
============================================

The `<style>` contains style information for a document, or part of a document. It contains CSS, which is applied to the contents of the document containing the `<style>` element.

The `<style>` element must be included inside the [`<head>`](head) of the document. In general, it is better to put your styles in external stylesheets and apply them using [`<link>`](link) elements.

If you include multiple `<style>` and `<link>` elements in your document, they will be applied to the DOM in the order they are included in the document — make sure you include them in the correct order, to avoid unexpected cascade issues.

In the same manner as `<link>` elements, `<style>` elements can include `media` attributes that contain [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries), allowing you to selectively apply internal stylesheets to your document depending on media features such as viewport width.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`type`  
This attribute defines the styling language as a MIME type (charset should not be specified). This attribute is optional and defaults to `text/css` if it is not specified; values other than the empty string or `text/css` are not used. **Note:** There is very little reason to include this attribute in modern web documents.

`media`  
This attribute defines which media the style should be applied to. Its value is a [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries), which defaults to `all` if the attribute is missing.

`nonce`  
A cryptographic nonce (number used once) used to whitelist inline styles in a [style-src Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/style-src). The server must generate a unique nonce value each time it transmits a policy. It is critical to provide a nonce that cannot be guessed as bypassing a resource’s policy is otherwise trivial.

`title`  
This attribute specifies [alternative style sheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets) sets.

### Deprecated attributes

 `scoped` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies that the styles only apply to the elements of its parent(s) and children.

This attribute may be re-introduced in the future per <https://github.com/w3c/csswg-drafts/issues/3547>. If you want to use the attribute now, you can use a [polyfill](https://github.com/samthor/scoped).

Examples
--------

### A simple stylesheet

In the following example, we apply a very simple stylesheet to a document:

    <!doctype html>
    <html>
    <head>
      <style>
        p {
          color: red;
        }
      </style>
    </head>
    <body>
      <p>This is my paragraph.</p>
    </body>
    </html>

### Multiple style elements

In this example we've included two `<style>` elements — notice how the conflicting declarations in the later `<style>` element override those in the earlier one, if they have equal [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity).

    <!doctype html>
    <html>
    <head>
      <style>
        p {
          color: white;
          background-color: blue;
          padding: 5px;
          border: 1px solid black;
        }
      </style>
      <style>
        p {
          color: blue;
          background-color: yellow;
        }
      </style>
    </head>
    <body>
      <p>This is my paragraph.</p>
    </body>
    </html>

### Including a media query

In this example we build on the previous one, including a `media` attribute on the second `<style>` element so it is only applied when the viewport is less than 500px in width.

    <!doctype html>
    <html>
    <head>
      <style>
        p {
          color: white;
          background-color: blue;
          padding: 5px;
          border: 1px solid black;
        }
      </style>
      <style media="all and (max-width: 500px)">
        p {
          color: blue;
          background-color: yellow;
        }
      </style>
    </head>
    <body>
      <p>This is my paragraph.</p>
    </body>
    </html>

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">Metadata content</a>, and if the <code>scoped</code> attribute is present: <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Text content matching the <code>type</code> attribute, that is <code>text/css</code>.</td></tr><tr class="odd"><td>Tag omission</td><td>Neither tag is omissible.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#metadata_content">metadata content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement"><code>HTMLStyleElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-style-element">HTML Living Standard<br />
<span class="small">The definition of 'style' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/document-metadata.html#the-style-element">HTML5<br />
<span class="small">The definition of 'style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <code>type</code> attribute becomes optional.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/present/styles.html#h-14.2.3">HTML 4.01 Specification<br />
<span class="small">The definition of 'style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`style`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`media`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`scoped`

19-35

No

55-61

This attribute was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

No

15-22

No

No

25-35

55-61

This attribute was hidden behind a pref because no other browsers support it (See [bug 1291515](https://bugzil.la/1291515)).

21-55

14-22

No

1.5-3.0

`title`

1

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`type`

1

12

1

Prior to 75, Firefox accepted any CSS media (MIME) type, with optional parameters. Starting in 75, this has been restricted to the string 'text/css', per the spec.

3

3.5

1

1

18

4

10.1

1

1.0

See also
--------

-   The [`<link>`](link) element, which allows us to apply external stylesheets to a document.
-   [Alternative Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style</a>
