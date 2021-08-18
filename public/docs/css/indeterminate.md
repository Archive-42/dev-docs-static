# :indeterminate

The `:indeterminate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) represents any form element whose state is indeterminate, such as checkboxes which have their HTML `indeterminate` attribute set to `true`, radio buttons which are members of a group in which all radio buttons are unchecked, and indeterminate [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) elements.

    /* Selects any <input> whose state is indeterminate */
    input:indeterminate {
      background: lime;
    }

Elements targeted by this selector are:

- `<input type="checkbox">` elements whose `indeterminate` property is set to `true` by [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- `<input type="radio">` elements, when all radio buttons with the same `name` value in the form are unchecked
- [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) elements in an indeterminate state

## Syntax

    :indeterminate

## Examples

### Checkbox & radio button

This example applies special styles to the labels associated with indeterminate form fields.

#### HTML

    <div>
      <input type="checkbox" id="checkbox">
      <label for="checkbox">This label starts out lime.</label>
    </div>
    <div>
      <input type="radio" id="radio">
      <label for="radio">This label starts out lime.</label>
    </div>

#### CSS

    input:indeterminate + label {
      background: lime;
    }

#### JavaScript

    var inputs = document.getElementsByTagName("input");

    for (var i = 0; i < inputs.length; i++) {
      inputs[i].indeterminate = true;
    }

### Progress bar

#### HTML

    <progress>

#### CSS

    progress {
      margin: 4px;
    }

    progress:indeterminate {
      opacity: 0.5;
      background-color: lightgray;
      box-shadow: 0 0 2px 1px red;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#selector-indeterminate">HTML Living Standard<br />
<span class="small">The definition of ':indeterminate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#selector-indeterminate">HTML5<br />
<span class="small">The definition of ':indeterminate' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines the semantics of HTML and constraint validation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#indeterminate">Selectors Level 4<br />
<span class="small">The definition of ':indeterminate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change.</td></tr></tbody></table>

BCD tables only load in the browser

- [Web forms — Working with user data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- The `<input type="checkbox">` element's `indeterminate` attribute
- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface which implements it.
- The [`:checked`](:checked) CSS selector lets you style checkboxes based on whether they're checked or not

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate</a>
