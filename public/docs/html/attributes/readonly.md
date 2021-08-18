HTML attribute: readonly
========================

**Draft**

This page is not complete.

The Boolean `readonly` attribute, when present, makes the element not mutable, meaning the user can not edit the control. If the `readonly` attribute is specified on an input element, because the user can not edit the input, the element does not participate in constraint validation.

The `readonly` attribute is supported by `text`, `search`, `url`, `tel`, `email`, `password`, `date`, `month`, `week`, `time`, `datetime-local`, and `number``<input>` types and the `<textarea>` form control elements. If present on any of these input types and elements, the `:read-only` pseudo class will match. If the attribute is not included, the `:read-write` pseudo class will match.

The attribute is not supported or relevant to `<select>` or input types that are already not mutable, such as [checkbox](../element/input/checkbox) and [radio](../element/input/radio) or cannot, by definition, start with a value, such as the [file](../element/input/file) input type. [range](../element/input/range) and [color](../element/input/color), as both have default values. It is also not supported on [hidden](../element/input/hidden) as it can not be expected that a user to fill out a form that is hidden. Nor is it supported on any of the button types, including `image`.

**Note:** Only text controls can be made read-only, since for other controls (such as checkboxes and buttons) there is no useful distinction between being read-only and being disabled, so the `readonly` attribute does not apply.

When an input has the `readonly` attribute, the [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only) pseudo-class also applies to it. Conversely, inputs that support the `readonly` attribute but don't have the attribute set match the [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write) pseudo-class.

### Attribute interactions

The difference between `disabled` and `readonly` is that read-only controls can still function and are still focusable, whereas disabled controls can not receive focus and are not submitted with the form and generally do not function as controls until they are enabled.

Because a read-only field cannot have it's value changed by a user interaction, `required` does not have any effect on inputs with the `readonly` attribute also specified.

The only way to modify dynamically the value of the readonly attribute is through a script.

**Note:** The `required` attribute is not permitted on inputs with the `readonly` attribute specified.

### Usability

Browsers display the `readonly` attribute...

### Constraint validation

If the element is readonly, then the element's value can not be updated by the user, and does not participate in constraint validation.

Example
-------

### HTML

    <div class="group">
      <input type="textbox" value="Some value" readonly="readonly"/>
      <label>Textbox</label>
    </div>
    <div class="group">
      <input type="date" value="2020-01-01" readonly="readonly"/>
      <label>Date</label>
    </div>
    <div class="group">
      <input type="email" value="Some value" readonly="readonly"/>
      <label>Email</label>
    </div>
    <div class="group">
      <input type="password" value="Some value" readonly="readonly"/>
      <label>Password</label>
    </div>
    <div class="group">
      <textarea readonly="readonly">Some value</textarea>
      <label>Message</label>
    </div>

### Result

Examples
--------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#attr-input-readonly">HTML Living Standard<br />
<span class="small">The definition of 'readonly attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#attr-input-readonly">HTML5<br />
<span class="small">The definition of 'readonly attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#the-readonly-attribute">HTML 5.1<br />
<span class="small">The definition of 'readonly attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.readonly`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only) and [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write)
-   [`<input>`](../element/input)
-   [`<select>`](../element/select)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/readonly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/readonly</a>
