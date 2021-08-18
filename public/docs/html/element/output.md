&lt;output&gt;: The Output element
==================================

The **HTML Output element** (`<output>`) is a container element into which a site or app can inject the results of a calculation or the outcome of a user action.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_listed">listed</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable">labelable</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_resettable">resettable</a> <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated element</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>status</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement"><code>HTMLOutputElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`for`  
A space-separated list of other elements’ [`id`](../global_attributes#attr-id)s, indicating that those elements contributed input values to (or otherwise affected) the calculation.

`form`  
The [`<form>`](form) element to associate the output with (its *form owner*). The value of this attribute must be the [`id`](../global_attributes#attr-id) of a `<form>` in the same document. (If this attribute is not set, the `<output>` is associated with its ancestor `<form>` element, if any.)

This attribute lets you associate `<output>` elements to `<form>`s anywhere in the document, not just inside a `<form>`. It can also override an ancestor `<form>` element.

`name`  
The element's name. Used in the [`form.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements) API.

The `<output>` value, name, and contents are NOT submitted during form submission.

Examples
--------

In the following example, the form provides a slider whose value can range between `0` and `100`, and an [`<input>`](input) element into which you can enter a second number. The two numbers are added together, and the result is displayed in the `<output>` element each time the value of any of the controls changes.

    <form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
      <input type="range" id="b" name="b" value="50" /> +
      <input type="number" id="a" name="a" value="10" /> =
      <output name="result" for="a b">60</output>
    </form>

Accessibility Concerns
----------------------

Many browsers implement this element as an `aria-live` region. Assistive technology will thereby announce the results of UI interactions posted inside it without requiring that focus is switched away from the controls that produce those results.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-output-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;output&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-output-element">HTML5<br />
<span class="small">The definition of '&lt;output&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`output`

10

≤18

4

No

11

7

Yes

Yes

4

?

Yes

Yes

`for`

10

≤18

4

No

11

7

Yes

Yes

4

?

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output</a>
