HTML attribute: required
========================

The Boolean `required` attribute which, if present, indicates that the user must specify a value for the input before the owning form can be submitted. The `required` attribute is supported by `text`, `search`, `url`, `tel`, `email`, `password`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `checkbox`, `radio`, `file`, [`<input>`](../element/input) types along with the [`<select>`](../element/select) and [`<textarea>`](../element/textarea) form control elements. If present on any of these input types and elements, the [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required) pseudo class will match. If the attribute is not included, the [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional) pseudo class will match.

The attribute is not supported or relevant to [range](../element/input/range) and [color](../element/input/color), as both have default values. It is also not supported on [hidden](../element/input/hidden) as it can not be expected that a user to fill out a form that is hidden. Nor is it supported on any of the button types, including `image`.

Note `color` and `range` don't support `required`, but type `color` defaults to `#000000`, and `range` defaults to the midpoint between `min` and `max` -- with `min` and `max` defaulting to 0 and 100 respectively in most browsers if not declared -- so always has a value.

In the case of a same named group of [radio](../element/input/radio) buttons, if a single radio button in the group has the `required` attribute, a radio button in that group must be checked, although it doesn't have to be the one with the attribute is applied. So to improve code maintenance, it is recommended to either include the `required` attribute in every same-named radio button in the group, or else in none.

In the case of a same named group of [checkbox](../element/input/checkbox) input types, only the checkboxes with the `required` attribute are required.

Note: Setting `aria-required="true"` tells a screen reader that an element (any element) is required, but has no bearing on the optionality of the element.

### Attribute interactions

Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### Usability

When including the `required` attribute, provide a visible indication near the control informing the user that the [`<input>`](../element/input), [`<select>`](../element/select) or [`<textarea>`](../element/textarea) is required. In addition, target required form controls with the [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required) pseudo-class, styling them in a way to indicate they are required. This improves usability for sighted users. Assistive technology should inform the user that the form control in mandatory based on the required attribute, but adding `aria-required="true"` doesn't hurt, in case the browser / screen reader combination does not support `required` yet.

### Constraint validation

If the element is required and the element's value is the empty string, then the element is suffering from <span class="page-not-created">`valueMissing`</span> and the element will match the [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) pseudo class.

Accessibility concerns
----------------------

Provide an indication to users informing them the form control is required. Ensure the messaging is multi-faceted, such as thru text, color, markings, and attribute, so that all users understand the requirements whether they have color blindness, cognitive differences, or are using a screen reader.

Example
-------

### HTML

    <form>
      <div class="group">
        <input type="text">
        <label>Normal</label>
      </div>
      <div class="group">
        <input type="text" required="required">
        <label>Required</label>
      </div>
      <input type="submit">
    </form>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#attr-input-required">HTML Living Standard<br />
<span class="small">The definition of 'required attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#attr-input-required">HTML5<br />
<span class="small">The definition of 'required attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#the-required-attribute">HTML 5.1<br />
<span class="small">The definition of 'required attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attributes.required`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   <span class="page-not-created">`validitystate.valuemissing`</span>
-   [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required) and [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional)
-   [`<input>`](../element/input)
-   [`<select>`](../element/select)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required</a>
