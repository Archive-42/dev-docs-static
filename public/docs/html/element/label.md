&lt;label&gt;
=============

The `<label>` represents a caption for an item in a user interface.

Associating a `<label>` with an [`<input>`](input) element offers some major advantages:

-   The label text is not only visually associated with its corresponding text input; it is programmatically associated with it too. This means that, for example, a screen reader will read out the label when the user is focused on the form input, making it easier for an assistive technology user to understand what data should be entered.
-   You can click the associated label to focus/activate the input, as well as the input itself. This increased hit area provides an advantage to anyone trying to activate the input, including those using a touch-screen device.

To associate the `<label>` with an `<input>` element, you need to give the `<input>` an `id` attribute. The `<label>` then needs a `for` attribute whose value is the same as the input's `id`.

Alternatively, you can nest the `<input>` directly inside the `<label>`, in which case the `for` and `id` attributes are not needed because the association is implicit:

    <label>Do you like peas?
      <input type="checkbox" name="peas">
    </label>

Other usage notes:

-   The form control that the label is labeling is called the *labeled control* of the label element. One input can be associated with multiple labels.
-   When a `<label>` is clicked or tapped and it is associated with a form control, the resulting `click` event is also raised for the associated control.

Attributes
----------

This element includes the [global attributes](../global_attributes).

`for`  
The [`id`](../global_attributes#attr-id) of a [labelable](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable) form-related element in the same document as the `<label>` element. The first element in the document with an `id` matching the value of the `for` attribute is the *labeled control* for this label element if it is a [labelable element](https://html.spec.whatwg.org/multipage/forms.html#category-label). If it is not labelable then the `for` attribute has no effect. If there are other elements that also match the `id` value, later in the document, they are not considered.

**Note**: A `<label>` element can have both a `for` attribute and a contained control element, as long as the `for` attribute points to the contained control element.

Styling with CSS
----------------

There are no special styling considerations for `<label>` elements — structurally they are simple inline elements, and so can be styled in much the same way as a [`<span>`](span) or [`<a>`](a) element. You can apply styling to them in any way you want, as long as you don't cause the text to become difficult to read.

Examples
--------

### Simple label example

    <label>Click me <input type="text"></label>

### Using the "for" attribute

    <label for="username">Click me</label>
    <input type="text" id="username">

Accessibility concerns
----------------------

### Interactive content

Don't place interactive elements such as [anchors](a) or [buttons](button) inside a `label`. Doing so makes it difficult for people to activate the form input associated with the `label`.

#### Don't

    <label for="tac">
      <input id="tac" type="checkbox" name="terms-and-conditions">
      I agree to the <a href="terms-and-conditions.html">Terms and Conditions</a>
    </label>

#### Do

    <label for="tac">
      <input id="tac" type="checkbox" name="terms-and-conditions">
      I agree to the Terms and Conditions
    </label>
    <p>
      <a href="terms-and-conditions.html">Read our Terms and Conditions</a>
    </p>

### Headings

Placing [heading elements](heading_elements) within a `<label>` interferes with many kinds of assistive technology, because headings are commonly used as [a navigation aid](heading_elements#navigation). If the label's text needs to be adjusted visually, use CSS classes applied to the `<label>` element instead.

If a [form](form), or a section of a form needs a title, use the [`<legend>`](legend) element placed within a [`<fieldset>`](fieldset).

#### Don't

    <label for="your-name">
      <h3>Your name</h3>
      <input id="your-name" name="your-name" type="text">
    </label>

#### Do

    <label class="large-label" for="your-name">
      Your name
      <input id="your-name" name="your-name" type="text">
    </label> 

### Buttons

An [`<input>`](input) element with a `type="button"` declaration and a valid `value` attribute does not need a label associated with it. Doing so may actually interfere with how assistive technology parses the button input. The same applies for the [`<button>`](button) element.

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#interactive_content">interactive content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form-associated_content">form-associated element</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, but no descendant <code>label</code> elements. No <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#form_labelable">labelable</a> elements other than the labeled control are allowed.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLabelElement"><code>HTMLLabelElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-label-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;label&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-label-element">HTML5<br />
<span class="small">The definition of '&lt;label&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.9.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;label&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-html40-971218/interact/forms.html#h-17.9.1">HTML 4.0 Specification<br />
<span class="small">The definition of '&lt;label&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`label`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`for`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label</a>
