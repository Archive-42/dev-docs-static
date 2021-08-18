&lt;summary&gt;: The Disclosure Summary element
===============================================

The **HTML Disclosure Summary element** (`<summary>`) element specifies a summary, caption, or legend for a [`<details>`](details) element's disclosure box. Clicking the `<summary>` element toggles the state of the parent `<details>` element open and closed.

<table><tbody><tr class="odd"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a> or one element of <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#heading_content">Heading content</a></td></tr><tr class="even"><td>Tag omission</td><td>None, both the start tag and the end tag are mandatory.</td></tr><tr class="odd"><td>Permitted parents</td><td>The <a href="details"><code>&lt;details&gt;</code></a> element.</td></tr><tr class="even"><td>Implicit ARIA role</td><td><code>button</code></td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

The `<summary>` element's contents can be any heading content, plain text, or HTML that can be used within a paragraph.

A `<summary>` element may *only* be used as the first child of a `<details>` element. When the user clicks on the summary, the parent `<details>` element is toggled open or closed, and then a `toggle` event is sent to the `<details>` element, which can be used to let you know when this state change occurs.

### Default label text

If a `<details>` element's first child is not a `<summary>` element, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will use a default string (typically "Details") as the label for the disclosure box.

### Default style

Per the HTML specification, the default style for `<summary>` elements includes `display: list-item`. This makes it possible to change or remove the icon displayed as the disclosure widget next to the label from the default, which is typically a triangle.

You can also change the style to `display: block` to remove the disclosure triangle.

See the [Browser compatibility](#browser_compatibility) section for details, as not all browsers support full functionality of this element yet.

Examples
--------

Below are some examples showing `<summary>` in use. You can find more examples in the documentation for the [`<details>`](details) element.

### Basic example

A simple example showing the use of `<summary>` in a [`<details>`](details) element:

    <details open>
      <summary>Overview</summary>
      <ol>
        <li>Cash on hand: $500.00</li>
        <li>Current invoice: $75.30</li>
        <li>Due date: 5/6/19</li>
      </ol>
    </details>

### Summaries as headings

You can use heading elements in `<summary>`, like this:

    <details open>
      <summary><h4>Overview</h4></summary>
      <ol>
        <li>Cash on hand: $500.00</li>
        <li>Current invoice: $75.30</li>
        <li>Due date: 5/6/19</li>
      </ol>
    </details>

This currently has some spacing issues that could be addressed using CSS.

**Warning:** Because the `<summary>` element has a default role of [button](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role) (which strips all roles from child elements), this example will not work for users of assistive technologies such as screen readers. The `<h4>` will have its role removed and thus will not be treated as a heading for these users.

### HTML in summaries

This example adds some semantics to the `<summary>` element to indicate the label as important:

    <details open>
      <summary><strong>Overview</strong></summary>
      <ol>
        <li>Cash on hand: $500.00</li>
        <li>Current invoice: $75.30</li>
        <li>Due date: 5/6/19</li>
      </ol>
    </details>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interactive-elements.html#the-summary-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;summary&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#the-summary-element">HTML 5.1<br />
<span class="small">The definition of '&lt;summary&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`summary`

12

79

49

No

15

6

4

Yes

49

14

Yes

Yes

`display_list_item`

89

89

49

No

75

No

No

89

49

No

No

No

See also
--------

-   [`<details>`](details)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary</a>
