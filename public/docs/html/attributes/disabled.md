disabled
========

The Boolean `disabled` attribute, when present, makes the element not mutable, focusable, or even submitted with the form. The user can neither edit nor focus on the control, nor its form control descendants. If the `disabled` attribute is specified on a form control, the element and its form control descendants do not participate in constraint validation. Often browsers grey out such controls and it won't receive any browsing events, like mouse clicks or focus-related ones.

The `disabled` attribute is supported by [`<button>`](../element/button), [`<command>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/command), [`<fieldset>`](../element/fieldset), [`<keygen>`](../element/keygen), [`<optgroup>`](../element/optgroup), [`<option>`](../element/option), [`<select>`](../element/select), [`<textarea>`](../element/textarea) and [`<input>`](../element/input).

This Boolean disabled attribute indicates that the user cannot interact with the control or its descendant controls. If this attribute is not specified, the control inherits its setting from the containing element, for example `fieldset`; if there is no containing element with the `disabled` attribute set, and the control itself does not have the attribute, then the control is enabled. If declared on an [`<optgroup>`](../element/optgroup), the select is still interactive (unless otherwise disabled), but none of the items in the option group are selectable.

Note: If a [`<fieldset>`](../element/fieldset) is disabled, the descendant form controls are all disabled, with the exception of form controls within the [`<legend>`](../element/legend).

When a supporting element has the `disabled` attribute applied, the [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled) pseudo-class also applies to it. Conversely, elements that support the `disabled` attribute but don't have the attribute set match the [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled) pseudo-class.

This Boolean attribute prevents the user from interacting with the button. If this attribute isn't set, the button can still be disabled from a containing element, for example `<fieldset>`; if there is no containing element with the `disabled` attribute set, then the button is enabled.

Firefox will, unlike other browsers, persist the dynamic disabled state of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.

### Attribute interactions

The difference between `disabled` and `readonly` is that read-only controls can still function and are still focusable, whereas disabled controls can not receive focus and are not submitted with the form and generally do not function as controls until they are enabled.

Because a disabled field cannot have its value changed, `required` does not have any effect on inputs with the `disabled` attribute also specified. Additionally, since the elements become immutable, most other attributes, such as `pattern`, have no effect, until the control is enabled.

**Note:** The `required` attribute is not permitted on inputs with the `disabled` attribute specified.

### Usability

Browsers display disabled form controls greyed as disabled form controls are immutable, won't receive focus or any browsing events, like mouse clicks or focus-related ones, and aren't submitted with the form.

If present on a supporting elements, the `:disabled` pseudo class will match. If the attribute is not included, the `:enabled` pseudo class will match. If the element doesn't support the disabled attribute, the attribute will have no effect, including not leading to being matched by the `:disabled` and `:enabled` pseudo classes.

### Constraint validation

If the element is `disabled`, then the element's value can not receive focus and cannot be updated by the user, and does not participate in constraint validation.

Examples
--------

When form controls are disabled, many browsers will display them in a lighter, greyed-out color by default. Here are examples of a disabled checkbox, radio button, [`<option>`](../element/option) and [`<optgroup>`](../element/optgroup), as well as some form controls that are disabled via the disabled attribute set on the ancestor `<fieldset>` element. The [`<option>`](../element/option)s are disabled, but the [`<select>`](../element/select) itself is not. We could have disable the entire [`<select>`](../element/select) by adding the attribute to that element rather than its descendants.

    <fieldset>
      <legend>Checkboxes</legend>
      <p><label>
        <input type="checkbox" name="chbox" value="regular"> Regular
      </label></p>
      <p><label>
        <input type="checkbox" name="chbox" value="disabled" disabled> disabled
      </label></p>
    </fieldset>

    <fieldset>
      <legend>Radio buttons</legend>
      <p><label>
        <input type="radio" name="radio" value="regular"> Regular
      </label></p>
      <p><label>
        <input type="radio" name="radio" value="disabled" disabled> disabled
      </label></p>
    </fieldset>

    <p>
     <label>Select an option:
      <select>
        <optgroup label="Group 1">
          <option>Option 1.1</option>
        </optgroup>
        <optgroup label="Group 2">
          <option>Option 2.1</option>
          <option disabled>Option 2.2</option>
          <option>Option 2.3</option>
        </optgroup>
        <optgroup label="Group 3" disabled>
          <option>Disabled 3.1</option>
          <option>Disabled 3.2</option>
          <option>Disabled 3.3</option>
        </optgroup>
      </select>
     </label>
    </p>

    <fieldset disabled>
      <legend>Disabled fieldset</legend>
      <p>
       <label>Name: <input type="name" name="radio" value="regular"> Regular </label>
      </p>
      <p>
       <label>Number: <input type="number"></label>
      </p>
    </fieldset>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#attr-input-disabled">HTML Living Standard<br />
<span class="small">The definition of 'disabled attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#attr-input-disabled">HTML5<br />
<span class="small">The definition of 'disabled attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#the-disabled-attribute">HTML 5.1<br />
<span class="small">The definition of 'disabled attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.disabled`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled) and [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/disabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/disabled</a>
