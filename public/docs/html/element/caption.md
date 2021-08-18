&lt;caption&gt;: The Table Caption element
==========================================

The `<caption>` specifies the caption (or title) of a table.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The end tag can be omitted if the element is not immediately followed by ASCII whitespace or a comment.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="table"><code>&lt;table&gt;</code></a> element, as its first descendant.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCaptionElement"><code>HTMLTableCaptionElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

### Deprecated attributes

The following attributes are deprecated and should not be used. They are documented below for reference when updating existing code and for historical interest only.

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute indicates how the caption must be aligned with respect to the table. It may have one of the following values:

`left`  
The caption is displayed to the left of the table.

`top`  
The caption is displayed above the table.

`right`  
The caption is displayed to the right of the table.

`bottom`  
The caption is displayed below the table.

**Usage note:** Do not use this attribute, as it has been deprecated. The [`<caption>`](caption) element should be styled using the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side) and [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align).

Usage notes
-----------

The `<caption>` element should be the first child of its parent [`<table>`](table) element.

When the `<table>` element that contains the `<caption>` is the only descendant of a [`<figure>`](figure) element, you should use the [`<figcaption>`](figcaption) element instead of `<caption>`.

Example
-------

This simple example presents a table that includes a caption.

    <table>
      <caption>Example Caption</caption>
      <tr>
        <th>Login</th>
        <th>Email</th>
      </tr>
      <tr>
        <td>user1</td>
        <td>user1@sample.com</td>
      </tr>
      <tr>
        <td>user2</td>
        <td>user2@sample.com</td>
      </tr>
    </table>

`table {background: red;}` do not alter caption. For that you need `display: block`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-caption-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;caption&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-caption-element">HTML5<br />
<span class="small">The definition of '&lt;caption&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/tables.html#h-11.2.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;caption&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`caption`

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

`align`

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

-   CSS properties that may be specially useful to style the [`<caption>`](caption) element:
    -   [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align), [`caption-side`](https://developer.mozilla.org/en-US/docs/Web/CSS/caption-side).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption</a>
